---
title: "dışarı aktarma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: vc-attr.export
dev_langs: C++
helpviewer_keywords: export attribute
ms.assetid: 70b3e848-fad6-4e09-8c72-be60ca72a4df
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 24619e3a0e707b40590b0ffb37b415629a18b1cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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
  
 Adlandırılmamış veriyorsanız `enum`s veya `struct`s, bunlar ile başlayan verilen adları olacaktır **__unnamed***x*, burada *x* sıralı bir sayıdır.  
  
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
|**Uygulandığı öğe:**|**birleşim**, `typedef`, `enum`, `struct`, veya`interface`|  
|**Yinelenebilir**|Hayır|  
|**Gerekli öznitelikler**|Yok.|  
|**Geçersiz öznitelikler**|Yok.|  
  
 Daha fazla bilgi için bkz: [öznitelik bağlamları](../windows/attribute-contexts.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Derleyici öznitelikleri](../windows/compiler-attributes.md)   
 [Typedef, Enum, Union ve Struct Öznitelikleri](../windows/typedef-enum-union-and-struct-attributes.md)   
