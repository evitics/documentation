===Creating a Variable===
```$name = "Colin Bookman";```

===Creating a function===
```
function foo($name) {
  echo "My name is: " . $name;
}

assert(foo("Colin") === "My name is: Colin");
```
===Creating a class===

==Public vs Private vs Protected==
  * Public: anyone either inside the class or outside can access them
  * Private: only the specified class can access them. Even subclasses will be denied access.
  * Protected: only the specified class and subclasses can access them

==Instantiated class==
```
Class Person {
  public $name,$age;
  private $race;
  public static $funFact = "A crocodile can't stick it's tongue out.";
  private function __construct ($name,$age,$race) {
    $this->name = $name;
    $this->age = $age;
    $this->race = $race;
  }
  public function whatsMyName() {
    echo "Your name is" . $this->name;
  }
  public function getRace() {
    return $this->race;
  }
  public function firstCharOfFunFact() {
    self::funFact[0];
  }
}

$colin = new Person("Colin",22,"White");
assert($colin->name === "Colin");
assert($colin->whatsMyName() === "Your name is Colin");
assert($colin::funFact === "A crocodile can't stick it's tongue out.");
//Doing $this->race will fail, as its private

==Static Methods in Class==
Class SQL {
  public $db = NULL;
  private static function connect($databaseName) {
    $this->db = new PDO('mysql:host=localhost;dbname=' . $databaseName, 'username', 'password');
  }
  public function __construct($databaseName) {
    self::connect($databaseName);
  }
  public function runQuery($sql, $params) {
    $query = $this->db->prepare($sql);
    $query->execute($params);
    //To fetch using the column names add the following
    $query->setFetchMode(PDO::FETCH_ASSOC);
    /*
      To fetch using numbers E.g: [0]
      $query->setFetchMode(PDO::FETCH_NUM);
    */
    if($query->rowCount() > 0) {
      echo "RESULTS!!!";
      return $query->fetchAll();
    } else {
      echo "NO RESULTS :(";
      return false;
    }
  }
  public static function getDbConn() { return $this->db; }
}

$sql = new SQL('jacketpages');
assert(sql::getDbConn() === $sql->db);
$queryRes = $sql->runQuery("SELECT * FROM `jacketpages`.`organizations` WHERE id = :id", array(":id" => $id))
if($queryRes) {
  echo "Successfully ran query;
  echo json_encode($queryRes);
} else {
  echo "Oh noes";
  echo json_encode($sql->db->errorInfo());
}
```
