---
title: _com_raise_error | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: _com_raise_error
dev_langs: C++
helpviewer_keywords: _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cfb51d4188917ebcdbad2fead13a9792875d2f11
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="comraiseerror"></a>_com_raise_error
**Microsoft özel**  
  
 Atan bir [_com_error](../cpp/com-error-class.md) hatasına yanıt.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      void __stdcall _com_raise_error(  
   HRESULT hr,  
   IErrorInfo* perrinfo = 0  
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `hr`  
 `HRESULT` bilgileri.  
  
 `perrinfo`  
 **IErrorInfo** nesnesi.  
  
## <a name="remarks"></a>Açıklamalar  
 `_com_raise_error`, hangi comdef.h içinde tanımlı bir kullanıcı tarafından yazılan aynı adı ve sürümünü prototip tarafından değiştirilebilir. Kullanmak istiyorsanız, bu yapılabilir `#import` ancak C++ özel durum işleme kullanmak istiyor musunuz. Bu durumda, kullanıcı sürümünde **_com_raise_error** yapmak karar verebilirsiniz bir `longjmp` veya bir ileti kutusu görüntüleme ve durdur. Derleyici COM destek kodu dönmek için beklemiyor çünkü kullanıcı sürümü, yine de vermemelidir.  
  
 Aynı zamanda [_set_com_error_handler](../cpp/set-com-error-handler.md) varsayılan hata işleme işlevini değiştirmek için.  
  
 Varsayılan olarak, `_com_raise_error` şu şekilde tanımlanır:  
  
```  
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {  
   throw _com_error(hr, perrinfo);  
}  
```  
  
**SON Microsoft özel**  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** comdef.h  
  
 **LIB:** varsa **wchar_t yerel tür olan** derleyici seçeneği üzerinde comsuppw.lib veya comsuppwd.lib kullanın. Varsa **wchar_t yerel tür olan** kapalı ise comsupp.lib kullanın. Daha fazla bilgi için bkz: [/ZC: wchar_t (wchar_t yerel tür olan)](../build/reference/zc-wchar-t-wchar-t-is-native-type.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici Global COM işlevleri](../cpp/compiler-com-global-functions.md)   
 [_set_com_error_handler](../cpp/set-com-error-handler.md)