# Postman API 自动化测试

 ## 1. 项目简介

     所有测试用例均使用 Postman 进行设计和编写，并通过其命令行工具 Newman 来执行，以便于集成到CI/CD流程中。

 ## 2. 技术栈与工具
    
     测试工具: Postman

     运行环境: Node.js

     命令行执行器: Newman

     测试报告: newman-reporter-htmlextra



 ## 4. 如何运行

### 4.1. 环境准备 (Prerequisites)


1.  **安装 Node.js**:

2.  **全局安装 Newman**:
    打开命令行工具，执行以下命令：
    ```bash
    npm install -g newman
    ```

3.  **全局安装 HTML报告生成器**:
    安装 `htmlextra` 报告器。
    ```bash
    npm install -g newman-reporter-htmlextra
    ```

### 4.2. 执行测试 (Running the Tests)

1.  执行以下命令来运行 `collections` 文件夹下的所有测试用例：

    ```bash
    newman run "collections\*.postman_collection.json" -e "environments\考试系统测试环境.postman_environment.json" -r cli,htmlextra
    ```
    
    **命令**:
    * `run "collections\*.postman_collection.json"`: 运行 `collections` 文件夹下所有以 `.postman_collection.json` 结尾的文件。
    * `-e "environments\..."`: 指定本次运行所使用的环境配置文件。
    * `-r cli,htmlextra`: 指定使用两种报告器，`cli` 表示在命令行实时输出结果，`htmlextra` 表示在结束后生成HTML报告。

## 5. 查看报告

测试运行完毕后，项目根目录下会自动生成一个名为 `newman` 的文件夹。打开它，找到里面的 `.html` 文件并用浏览器打开，即可看到本次测试的详细报告。
