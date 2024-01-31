---------------------------------------------------------------------------
ValueError                                Traceback (most recent call last)
~\AppData\Local\Temp\ipykernel_10560\4078715308.py in ?()
----> 1 print[df]

~\miniconda3\envs\forageJPMorgan\Lib\site-packages\pandas\core\frame.py in ?(self, key)
   4073             return self._getitem_slice(key)
   4074 
   4075         # Do we have a (boolean) DataFrame?
   4076         if isinstance(key, DataFrame):
-> 4077             return self.where(key)
   4078 
   4079         # Do we have a (boolean) 1d indexer?
   4080         if com.is_bool_indexer(key):

~\miniconda3\envs\forageJPMorgan\Lib\site-packages\pandas\core\generic.py in ?(self, cond, other, inplace, axis, level)
  10974                         stacklevel=2,
  10975                     )
  10976 
  10977         other = common.apply_if_callable(other, self)
> 10978         return self._where(cond, other, inplace, axis, level)

~\miniconda3\envs\forageJPMorgan\Lib\site-packages\pandas\core\generic.py in ?(self, cond, other, inplace, axis, level, warn)
  10663                     raise ValueError(msg.format(dtype=cond.dtype))
  10664             else:
  10665                 for _dt in cond.dtypes:
  10666                     if not is_bool_dtype(_dt):
> 10667                         raise ValueError(msg.format(dtype=_dt))
  10668                 if cond._mgr.any_extension_types:
  10669                     # GH51574: avoid object ndarray conversion later on
  10670                     cond = cond._constructor(

ValueError: Boolean array expected for the condition, not int64
