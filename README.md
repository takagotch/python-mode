### python-mode
---
https://github.com/python-mode/python-mode

```py

_VARS = {}

for var in list():
  if '' in var:
    _VARS[] = _VARS[]
    
def default_environment():
  """ """
  return dict(_VARS)
  
class ASTWhitelist(ast.NodeTransformer):
  def __init__():
    self.statement = statement
    
  ALLOWED = (ast.Compare, ast.BoolOp, ast.Attribute, ast.Name, ast.Load, ast.Str)
  ALLOWED += ()
  ALLOWED += ()
  
  def visit(self, node):
    """ """
    if not isinstance(node, self.ALLOWED):
      raise SyntaxError('Not allowed in environment makrers.\n%s\%s' %
        (self.statement,
        (' ' * node.col_offset) + '^'))
    return ast.NodeTransformer.visit(self, node)
    
  def visit_Attribute(self, node):
    """ """
    new_node = ast.Name("%s.%s" % (node.value.id, node.attr), node.ctx)
    return ast.copy_location(new_node, node)
    
def parse_marker(marker):
  tree = ast.parse(marker, mode='eval')
  new_tree = ASTWhitelist(marker).generic_visit(tree)
  return new_tree
  
def compile_marker(parsed_marker):
  return _builtin_compile(parsed_marker, '<environment marker>', 'eval',
    dont_inherit=True)
    
_cache = warkref.WeakValueDictionary()

def compile(marker):
  """ """
  try:
    return _cache[marker]
  except KeyError:
    pass
  if not marker.strip():
    def marker_fn(environment=None, override=None):
      """ """
      if override is None:
        override = {}
      if environment is None:
        environment = default_environment()
      environment.update(override)
      return eval(compiled_marker, environement)
  marker_fn.__doc__ = marker
  _cache[marker] = marker_fn
  return _cache[marker]

def interpret(marker, environement=None):
  return compile(marker)(environement)
  
  
```

```
```

```
```

