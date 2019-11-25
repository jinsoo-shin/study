# theme 적용하기

{% embed url="https://github.com/iTimeTraveler/hexo-theme-hipaper" %}

> 압축풀고 폴더를 theme 이름으로 변경하기.

![](../.gitbook/assets/image%20%289%29.png)

> hexo 기본 폴더 내의 theme에 넣기

![](../.gitbook/assets/image%20%286%29.png)

![](../.gitbook/assets/image%20%2822%29.png)

> blog / themes / \_config.yml

{% code title="\_config.yml 수정" %}
```text
# Extensions
## Plugins: http://hexo.io/plugins/
## Themes: http://hexo.io/themes/
theme: hipaper
```
{% endcode %}

```text
deploy:
  repo : https://github.com/jinsoo-shin/jinsoo-shin.github.io.git
  branch: master
  type: git
```

![](../.gitbook/assets/image%20%282%29.png)

## github 배포하기

```text
hexo generate  // 정적 리소스 생성
- npm install hexo-deployer-git --save
- hexo deploy  // 배포하기

```

