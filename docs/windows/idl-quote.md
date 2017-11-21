---
title: idl_quote | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.idl_quote
dev_langs: C++
helpviewer_keywords: idl_quote attribute
ms.assetid: a370e1b7-948b-4e67-9a25-58facf24e4c9
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8ca11d9b92ba1dd0dc7f5437bf1dec812f2edfcc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="idlquote"></a>idl_quote
Visual C++ geçerli sürümde desteklenmez IDL yapıları kullanmanıza olanak sağlar ve bunları oluşturulan .idl dosyasına geçirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      [ idl_quote(  
   text  
) ]  
```  
  
#### <a name="parameters"></a>Parametreler  
 *metin*  
 Oluşturulan .idl dosyasına derleyici hatası dönmeden geçmesine Visual C++ Derleyici düşündüğünüz öznitelik adı.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsa **idl_quote** C++ özniteliği kullanılır (noktalı virgül ile ayraç sonra), tek başına bir özniteliği olarak sonra *metin* birleştirilmiş .idl dosya olarak yerleştirilir. Varsa **idl_quote** bir simge üzerinde kullanılan *metin* bu simge için öznitelik bloğu içinde yerleştirilir.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod nasıl desteklenmeyen bir öznitelik belirtebilirsiniz gösterir (kullanarak **içinde**, desteklendiği) nasıl tanımlamak ve bir tanımsız .idl yapısıyla kullanın:  
  
```  
// cpp_attr_ref_idl_quote.cpp  
// compile with: /LD  
#include <unknwn.h>  
[module(name="MyLibrary")];  
  
[export]  
struct MYFLOT {  
   int i;  
};  
  
[export]  
struct MYDUB {  
   int i;  
};  
  
[idl_quote("typedef union _S1_TYPE switch (long l1) U1_TYPE { case 1024: \  
struct MYFLOT f1; case 2048: struct MYDUB d2; } S1_TYPE;") ];  
  
typedef struct _S1_TYPE {   
   long l1;   
  
union {   
   MYFLOT f1; MYDUB d2; } U1_TYPE;   
} S1_TYPE;  
  
[uuid("2F5F63F1-16DA-11d2-9E7B-00C04FB926DA"), object]  
__interface IStatic{  
   HRESULT Func1([idl_quote("in")] int i);  
   HRESULT func( S1_TYPE* myStruct );  
};  
```  
  
 Bu kod MYFLOT ve MYDUB neden olur ve *metin* oluşturulan .idl dosyasında yerleştirilecek girişi. *Adı* parametresi zorlar *metin* başvuruda bulunan her şeyi önce yerleştirilecek *adı* oluşturulan .idl dosyasındaki. *Bağımlılıkları* parametre zorlar önce yerleştirilecek bağımlılık liste tanımları *metin* oluşturulan .idl dosyasındaki.  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|Her yerden|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [IDL öznitelikleri](../windows/idl-attributes.md)   
 [Tek başına öznitelikler](../windows/stand-alone-attributes.md)   
