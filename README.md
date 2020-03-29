## 1. Подготовка к установке  


### 1.1 Склонируйте репозиторий на локальную машину командой:  
```
git clone https://github.com/Uladzimir-Kuchynski/Testing_task_Hello
cd Testing_task_Hello
```

### 1.2 Расшифруйте приватный ключ `centos_key` для доступа к удалённой машине (пароль будет отправлен по средством e-mail) и установить права:  
``` 
ansible-vault decrypt centos_key
chmod 600 centos_key
```

## 2. Установка  

### 2.1 Установка со значением по умолчанию  
Параметр `user_name` (он же параметр <Name>) находится в переменных по умолчанию роли в директории `hello_role/defaults/main.yml`. Выполните следующую команду для установки со значкением по умолчанию:  
```
ansible-playbook -i inventory hello_playbook.yml
```

### 2.2 Установка с новым значением из зашифрованного файла, который зашифрован при помощи ansible-vault. Выполните команду:  
```
ansible-playbook -i inventory --tags=create_index --ask-vault-pass --extra-vars @vars.yml  hello_playbook.yml
```

## 3. Проверка результатов  
Перейти в браузере на проверочную [страницу](http://epbyminw2603-v1.minsk.epam.com/) и нажать в открывшейся вкладке Ctrl+F5.
