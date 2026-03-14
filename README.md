# Домашнее задание к занятию «Ветвления в Git»

Задание «Ветвление, merge и rebase»

Commit : "Initial Commit"

Предположим, что есть задача — написать скрипт, выводящий на экран параметры его запуска. Давайте посмотрим, как будет отличаться работа над этим скриптом с использованием ветвления, merge и rebase.  

Используемые команды:

1. Создание файлов и первый коммит  

git add branching/merge.sh branching/rebase.sh  
git commit -m "prepare for merge and rebase"  
git push origin main  

2. Ветка git-merge  

git add branching/merge.sh  
git commit -m "merge: @ instead *"  
git push -u origin git-merge  

git add branching/merge.sh  
git commit -m "merge: use shift"  
git push  

3. Изменение main  

git add branching/rebase.sh  
git commit -m "main: update rebase.sh"  
git push origin main  

4. Ветка git-rebase от старого коммита  

git log --oneline  
git checkout HASH  
git checkout -b git-rebase  

git add branching/rebase.sh
git commit -m "git-rebase 1"
git push -u origin git-rebase

git add branching/rebase.sh  
git commit -m "git-rebase 2"  
git push  

5. Merge ветки git-merge  

git checkout main  
git merge git-merge  
git push origin main  

6. Rebase ветки git-rebase  

git checkout git-rebase  
git rebase -i main  

git add branching/rebase.sh  
git rebase --continue  

git push -u origin git-rebase -f  

7. Финальный merge в main  
   
git checkout main  
git merge git-rebase  
git push origin main  

### Чем merge отличается от rebase в этом задании

### Merge  

- сохраняет реальную историю;  
- проще и безопаснее;  
- часто создаёт merge-коммит;  
- удобен для командной работы.  

### Rebase  

- делает историю линейной и красивой;  
- переписывает коммиты;  
- после него обычно нужен push -f;  
- при конфликтах может быть сложнее.  