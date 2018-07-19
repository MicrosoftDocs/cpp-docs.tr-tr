---
title: _com_raise_error | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _com_raise_error
dev_langs:
- C++
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f38a0d97b90f1512e5f16b3bd147bda3e0614e4f
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/10/2018
ms.locfileid: "37948111"
---
# <a name="comraiseerror"></a>_com_raise_error
**Microsoft'a özgü**  
  
 Oluşturur bir [_com_error](../cpp/com-error-class.md) yanıt olarak bir hata.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
void __stdcall _com_raise_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = 0  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 *İK*  
 HRESULT bilgileri.  
  
 *perrinfo*  
 `IErrorInfo` nesne.  
  
## <a name="remarks"></a>Açıklamalar  
 `_com_raise_error`, tanımlanan \<comdef.h >, bir kullanıcı tarafından yazılan sürümü aynı ada ve prototip tarafından değiştirilebilir. Kullanmak istiyorsanız bu yapılabilir `#import` ancak C++ özel durum işleme kullanmak istemiyorsanız. Bu durumda, kullanıcı sürümünde `_com_raise_error` yapmak karar verebilirsiniz bir `longjmp` veya bir ileti kutusu görüntüleme ve durdur. Derleyici COM destek kodunu döndürmek için bunu beklemiyor çünkü kullanıcı sürümüdür, ancak döndürmemelidir.  
  
 Ayrıca [_set_com_error_handler](../cpp/set-com-error-handler.md) varsayılan hata işleme işlevinizi değiştirilecek.  
  
 Varsayılan olarak, `_com_raise_error` şu şekilde tanımlanır:  
  
```cpp  
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {  
   throw _com_error(hr, perrinfo);  
}  
```  
  
**END Microsoft özgü**  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** \<comdef.h >  
  
 **Lib:** varsa **wchar_t yerel tür olan** derleyici seçeneği açıktır, comsuppw.lib veya comsuppwd.lib kullanın. Varsa **wchar_t yerel tür olan** kapalıysa, comsupp.lib kullanın. Daha fazla bilgi için [/ZC: wchar_t (wchar_t yerel türü olduğu)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Global COM işlevleri](../cpp/compiler-com-global-functions.md)   
 [_set_com_error_handler](../cpp/set-com-error-handler.md)