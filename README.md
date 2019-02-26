# Test Flow

- develop changed  2019年02月26日10:51:22

- feat-1 added 2019年02月26日10:53:35

- feat -1 finished 2019年02月26日10:57:42

 - 拉取feat-1之后，修改了develop，此时 feat-1 执行flow finish时会合并冲突，手动修复冲突后，feat-1依然保留。

 - 手动删除feat-1，提示无法删除远端，是因为github default branch 设置为了feat1,更改为其他分支可删；

	```shell
	SENRSL:test-flow senrsl$ git branch -a
	  develop
	* feature/Feature-1
	  master
	  remotes/origin/develop
	  remotes/origin/feature/Feature-1
	SENRSL:test-flow senrsl$ git branch
	* develop
	  feature/Feature-1
	  master
	SENRSL:test-flow senrsl$ git branch -D feature/Feature-1
	Deleted branch feature/Feature-1 (was c9cf91a).
	SENRSL:test-flow senrsl$ git push origin --delete feature/Feature-1
	To github.com:senRsl/test-flow.git
	 ! [remote rejected] feature/Feature-1 (refusing to delete the current branch: refs/heads/feature/Feature-1)
	error: failed to push some refs to 'git@github.com:senRsl/test-flow.git'
	SENRSL:test-flow senrsl$ 
	```

- feat-2 added 2019年02月26日11:03:00
 - 执行 git flow finish,合并此分支至develop成功后自动删除此分支；

- feat-3 added 2019年02月26日11:05:42