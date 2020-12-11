#### 先序遍历

```c++
void gotoleft(TreeNode* p,stack<TreeNode*> &s) {
	while (p)
	{
		cout << p->data << " ";
		s.push(p->rightchild);
		p = p->leftchild;
	}
}
void pre_traversal(TreeNode* root) {
	stack<TreeNode*> s;
	while (true)
	{
		gotoleft(root, s);
		if (s.empty()) break;
		root = s.top();
		s.pop();
	}
}
```

```c++
void pre_trsversal(TreeNode* x)
{
	stack<TreeNode*> s;
    s.push(x);
    while(!s.empty())
    {
        x=s.top();
        s.pop();
        if(x==NULL)
        {
            continue;
        }
        else
        {
            cout<<x->data<<" ";
            s.push(x->rightchild);
            s.push(x->leftchild);
        }
    }
        
}
```

#### 中序遍历

```c++
void gotoleft(TreeNode* p,stack<TreeNode*> &s) {
	while (p)
	{
		s.push(p);
		p = p->leftchild;
	}
}
void in_traversal(TreeNode* root) {
	stack<TreeNode*> s;
	while (true)
	{
		gotoleft(root, s);
		if (s.empty()) break;
		root = s.top();
		s.pop();
		cout << root->data << " ";
		root = root->rightchild;
	}
}
```

#### 层次遍历

```c++
void cengcibianli(TreeNode* x) {
	queue<TreeNode*> q;
	q.push(x);
	while (true)
	{
		x = q.front();
		q.pop();
		cout << x->data << " ";
		if (x->leftchild) q.push(x->leftchild);
		if (x->rightchild) q.push(x->rightchild);
		if (q.empty()) break;
	}
}
```

