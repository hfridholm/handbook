# Conventions

## Naming

Functions that calculates the number of items in an array should be called `items_count` and return the variable `item_count`. The small difference between the two is reserved for distinguish between functions and variables.

## Terminology

`item_count` is the number of items in an array, not `item_amount`

## Coding Styles

### Nesting

Bad
```c
int function()
{
  if(function_1())
  {
    if(function_2())
    {
      if(function_3())
      {
        return 0; 
      }
      else return 3;
    }
    else return 2;
  }
  else return 1;
}
```

Good
```c
int function()
{
  if(!function_1()) return 1;

  if(!function_2()) return 2;

  if(!function_3()) return 3;

  return 0;
}
```

Bad
```c
int function()
{
  while(something)
  {
    if(function_1())
    {
      if(function_2())
      {
        return 0;
      }
    }
  }
}
```

Good
```c
int function()
{
  while(something)
  {
    if(!function_1()) continue;

    if(!function_2()) continue;

    return 0;
  }
}

// or

int function()
{
  while(something)
  {
    if(!function_1()) continue;

    if(function_2()) return 0;
  }
}
```
