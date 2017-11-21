---
title: '&lt;param&gt; (Visual C++) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- param
- <param>
dev_langs: C++
helpviewer_keywords:
- param C++ XML tag
- <param> C++ XML tag
ms.assetid: 66c1a1c3-4f98-4bcf-8c7d-9a40308982fb
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 21dcb436c58bc3823092ba7c03511bdf04fba9d4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltparamgt-visual-c"></a>&lt;param&gt; (Visual C++)
\<Param > etiketi açıklamasında bir yöntem bildirimi için parametrelerden biri yönteminde açıklamak için kullanılmalıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<param name='name'>description</param>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `name`  
 Yöntem parametresinin adı.  Ad, tek veya çift tırnak işaretleri içine alın.  Derleyici bulamadı, bir uyarı verir `name`.  
  
 `description`  
 Parametresi için bir açıklama.  
  
## <a name="remarks"></a>Açıklamalar  
 Metni \<param > etiketi IntelliSense içinde görüntülenir [Nesne Tarayıcısı](http://msdn.microsoft.com/en-us/f89acfc5-1152-413d-9f56-3dc16e3f0470)ve kod açıklama Web raporu.  
  
 İle derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) bir dosyaya işlem belgesi açıklamaları için.  
  
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
 [XML belgeleri](../ide/xml-documentation-visual-cpp.md)