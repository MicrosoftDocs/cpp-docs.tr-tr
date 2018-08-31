---
title: '&lt;param&gt; (Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- param
- <param>
dev_langs:
- C++
helpviewer_keywords:
- param C++ XML tag
- <param> C++ XML tag
ms.assetid: 66c1a1c3-4f98-4bcf-8c7d-9a40308982fb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f8fae2d8af1b7121290bfbd42b2668afc50034c
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43217259"
---
# <a name="ltparamgt-visual-c"></a>&lt;param&gt; (Visual C++)
\<Param > Etiket kullanılmalıdır yöntemi bildirimi için açıklama parametrelerden biri yöntemi tanımlamak için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<param name='name'>description</param>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `name`  
 Bir yöntem parametresi adı.  Ad, tek veya çift tırnak içine alın.  Değil bulamazsa, derleyici bir uyarı verir `name`.  
  
 `description`  
 Parametre için bir açıklama.  
  
## <a name="remarks"></a>Açıklamalar  
 Metni \<param > etiketi IntelliSense içinde gösterilecek [Nesne Tarayıcısı](https://msdn.microsoft.com/f89acfc5-1152-413d-9f56-3dc16e3f0470)ve kod açıklaması Web raporu.  
  
 Derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.  
  
## <a name="example"></a>Örnek  
  
```  
// xml_param_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_param_tag.dll  
/// Text for class MyClass.  
public ref class MyClass {  
   /// <param name="Int1">Used to indicate status.</param>  
   void MyMethod(int Int1) {  
   }  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Belgeleri](../ide/xml-documentation-visual-cpp.md)