---
title: dışarı aktarma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- vc-attr.export
dev_langs:
- C++
helpviewer_keywords:
- export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 67b71639fc0b7d0039f5665d2cc187191ac14baf
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874609"
---
# <a name="export"></a>dışarı aktar
Bir veri yapısı .idl dosyasında yerleştirilmesini neden olur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
[export]  
  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Verme** C++ öznitelik .idl dosyasında yerleştirilecek ve ardından herhangi bir dil ile kullanmak için kullanılabilir hale getirir ikili ile uyumlu bir biçimde türü kitaplığında kullanılabilir olması için bir veri yapısı neden olur.  
  
 Uygulayamazsınız **verme** sınıfı yalnızca Genel üyeler olsa bile bir sınıfa öznitelik (denk bir `struct`).  
  
 Adlandırılmamış veriyorsanız `enum`s veya `struct`s, bunlar ile başlayan verilen adları olacaktır **__unnamed *** x*, burada *x* sıralı bir sayıdır.  
  
 Tür tanımları dışa aktarma için geçerli olan temel türleri, yapılar, birleşimler, numaralandırmalar veya tanımlayıcıları yazın.  Bkz: [typedef](http://msdn.microsoft.com/library/windows/desktop/aa367287) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kodu nasıl kullanılacağını gösterir **verme** özniteliği:  
  
```  
// cpp_attr_ref_export.cpp  
// compile with: /LD  
[module(name="MyLibrary")];  
  
[export]  
struct MyStruct {  
   int i;  
};  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
### <a name="attribute-context"></a>Öznitelik bağlamı  
  
|||  
|-|-|  
|**Uygulandığı öğe:**|**birleşim**, `typedef`, `enum`, `struct`, veya `interface`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici öznitelikleri](../windows/compiler-attributes.md)   
 [Typedef, Enum, Union ve Struct Öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
