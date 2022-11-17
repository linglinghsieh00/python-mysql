在現今很多網站，都會透過API(Application Programming Interface)的方式來提供服務，讓用呼端能夠藉由這個介面存取其資料，進行多樣化的應用開發。
以KKBOX Open API為例，實作一個簡單的專案，示範Python如何存取音樂排行榜API，並且可以讓使用者選擇想聽的排行榜類別，試聽其中的歌曲。


#什麼是API


API(Application Programming Interface)想像是一個大門，要進入存取必須提供合法的帳號及密碼，才能拿到存取憑證(Access Token)，
之後要存取門後的API資源，只要帶著這個憑證，就可以進行存取。
API就是一組網址，透過HTTP協定來和用戶端進行溝通。


#專案前置準備
透過 pipenv 套件管理工具來為專案建立虛擬環境及安裝requests套件(Package)
什麼是Pipenv?
Pipenv 是一個簡單、更快速的 Python 套件管理工具，整合Pipfile, pip, virtualenv，我們需要一個乾淨環境來開發，以往會使用 virtualenv 建一個虛擬環境，再透過 pip 以及 requirements.txt 去管理套件的版本。
現在只需要一個 pipenv 下指令就可以幫我們解決套件管理的問題，專注於開發上面就好，不需要再分別使用 pip 跟virtualenv。

建立虛擬環境的幾個好處:
不同專案可使用不同版本相同套件，且不互相影響，可避免版本衝突。
在虛擬環境裡，pip 安裝的套件會被放在虛擬環境中，每個專案可擁有獨立環境。
套件版本升級時不會影響到其他的專案。

終端機執行：
安裝
 pip install pipenv
進入專案資料夾中
  mkdir env_project    　　　// 建立指定檔名的資料夾(自行命名)
  pipenv install             //安裝虛擬環境
  cd env_project　　　　　　　// 移動到專案資料夾
  pipenv shell              // 啟動虛擬環境
安裝套件
  pipenv install requests　　// 安裝request套件(自行安裝其他套件)
  pipenv install flask
 基本命令：
  exit //退出虛擬環境
  pipenv uninstall //卸載
  
 如果一開始專案沒有準備Pipfile跟Pipfile.lock，在執行pipenv install時會自動產生檔案，裡面記錄了該專案所用到的套件、使用的版本等各種依賴資訊。
 因此日後就算版本更新，或是提供出去的使用者版本不相容、缺少套件，都可以透過這兩個檔案內的資訊，重新下載安裝需要的依賴。
  pip3 list //看已載的套件
  pipenv --venv 查看虛擬環境放置的路徑(此為套件、直譯器放置的位置，每個虛擬環境的路經皆不同)，並將結果記下來

 
