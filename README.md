# gudusoft
Gudu Software Repository

## 📦 GSP SQL Parser (`gsqlparser`)

This repository contains the Maven package `gsqlparser`, a powerful SQL parser library that supports multiple database dialects such as Oracle, SQL Server, MySQL, PostgreSQL, and more.

---

## 📥 How to Use This Package from GitHub Packages

### ① Add the dependency:
```xml
<dependency>
  <groupId>gudusoft</groupId>
  <artifactId>gsqlparser</artifactId>
  <version>3.0.9.0</version>
</dependency>
```

### ② Add the GitHub Packages repository:
```xml
<repositories>
  <repository>
    <id>github</id>
    <name>GitHub Packages - sqlparser/gudusoft</name>
    <url>https://maven.pkg.github.com/sqlparser/gudusoft</url>
  </repository>
</repositories>
```

---

### ③ Configure authentication in `settings.xml`:

> ⚠️ GitHub Packages requires authentication to download packages — even for public repositories.

Edit or create your Maven `settings.xml` file at `~/.m2/settings.xml`:

```xml
<settings>
  <servers>
    <server>
      <id>github</id>
      <username>YOUR_GITHUB_USERNAME</username>
      <password>YOUR_PERSONAL_ACCESS_TOKEN</password>
    </server>
  </servers>
</settings>
```

#### 🔐 Notes:
- `YOUR_GITHUB_USERNAME`: your GitHub username
- `YOUR_PERSONAL_ACCESS_TOKEN`: a [GitHub PAT](https://github.com/settings/tokens) with at least the `read:packages` scope
- The `<id>github</id>` must match the `<repository><id>` in your `pom.xml`

---

## 📚 Example Usage

```java
TGSqlParser parser = new TGSqlParser(EDbVendor.dbvmysql);
parser.sqltext = "SELECT * FROM users";
int result = parser.parse();
if (result != 0) {
    System.out.println(parser.getErrormessage());
    return;
} else {
    System.out.println(parser.getSqlstatements().get(0).toString());
}
```

---

## 🔗 More Information

- Website: [https://www.sqlparser.com](https://www.sqlparser.com)
- Documentation: [https://docs.sqlparser.com](https://docs.sqlparser.com)
- Maven Artifacts: [https://github.com/sqlparser/gudusoft/packages](https://github.com/sqlparser/gudusoft/packages)
