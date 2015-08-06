# Ruby on Rails 기반 프로젝트 개발용 가상 머신

## Requirements

- [VirtualBox](https://www.virtualbox.org/)
- [Vagrant](http://vagrantup.com/)
- vagrant-librarian-chef-nochef 플러그인

## 가상 머신 빌드

```
$ git clone https://github.com/TheWhaleGames/railsbox.git
$ cd railsbox
$ vagrant up
```

## Box에 포함된 것

- apt
- nodejs
- ruby_build
- rbenv
- vim
- MySQL
- SQLite3