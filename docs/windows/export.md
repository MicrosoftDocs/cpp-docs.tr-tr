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
ms.openlocfilehash: 48c4a645456e3b3c0556dfed268ce911e5799fc3
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/06/2018
ms.locfileid: "39569423"
---
# <a name="export"></a>dışarı aktar
Bir veri yapısı .idl dosyasında yerleştirilmesine neden olur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
[export]  
```  
  
## <a name="remarks"></a>Açıklamalar  
 **Dışarı** C++ öznitelik, bir veri yapısı .idl dosyasına yerleştirilmesini ve herhangi bir dil ile kullanmak için kullanılabilir hale getirir ikili ile uyumlu bir biçimde tür kitaplığında kullanılabilir olması için neden olur.  
  
 Uygulayamazsınız **dışarı** sınıfı yalnızca Genel üyeler olsa bile bir sınıf özniteliği (denk bir **yapı**).  
  
 Adsız dışarı aktarırsanız **enum**s veya **yapı**s, bunlar ile başlayan adlar olacaktır **__unnamed *** x*burada *x* bir sıralı sayı.  
  
 Tür tanımları dışarı aktarma için geçerli olan temel türleri, yapılar, birleşimler, numaralandırmalar veya tanımlayıcıları yazın.  Bkz: [typedef](http://msdn.microsoft.com/library/windows/desktop/aa367287) daha fazla bilgi için.  
  
## <a name="example"></a>Örnek  
 Aşağıdaki kod nasıl kullanılacağını gösterir **dışarı** özniteliği:  
  
```cpp  
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
|**İçin geçerlidir**|**birleşim**, **typedef**, **enum**, **yapı**, veya **arabirimi**|  
|**Tekrarlanabilir**|Hayır|  
|**Gerekli öznitelikleri**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici öznitelikleri](../windows/compiler-attributes.md)   
 [Typedef, Enum, Union ve Struct Öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   