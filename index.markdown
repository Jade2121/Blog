---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---
<!-- Gitalk start -->
<div id="gitalk-container"></div> <link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/gitalk@1/dist/gitalk.css">
<script src="https://cdn.jsdelivr.net/npm/gitalk@1/dist/gitalk.min.js"></script> 
<script>
    var gitalk  = new Gitalk ({
        id: window.location.pathname,   // Ensure uniqueness and length less than 50
        clientID: '{ {site.comment_gitalk_clientId} }',
        clientSecret: '{ {site.comment_gitalk_clientSecret} }',
        repo: '{ {site.comment_gitalk_repo} }',
        owner: '{ {site.github_username} }',
        admin: ['{ {site.github_username} }'],
		    distractionFreeMode: false  // Facebook-like distraction free mode
    })
    gitalk.render('gitalk-container')
# Gitalk settings
comment_gitalk_clientId: 016b5ca4b67c62e4bcb8
comment_gitalk_clientSecret: ecb8315f37e53fa1ea812bdc9a7bd88220497116
comment_gitalk_repo: jade2121.github.io
github_username: jade2121
</script> 
<!-- Gitalk end -->
