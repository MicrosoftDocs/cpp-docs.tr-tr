---
title: '&lt;c&gt; (Visual C++) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: <c>
dev_langs: C++
helpviewer_keywords:
- <c> C++ XML tag
- c C++ XML tag
ms.assetid: 3b23fc0f-e10d-4dd0-b197-48a46cbddd9f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d44d1fccb0a6fdbcedff641982033bfdee4adc6f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltcgt-visual-c"></a>&lt;c&gt; (Visual C++)
\<c > etiketi belirten bir açıklama metni kodu olarak işaretlenmelidir. Kullanım [ \<kodu >](../ide/code-visual-cpp.md) birden fazla satır kodu olarak belirtmek için.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<c>text</c>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `text`  
 Kod olarak belirtmek istediğiniz metin.  
  
## <a name="remarks"></a>Açıklamalar  
 İle derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) bir dosyaya işlem belgesi açıklamaları için.  
  
## <a name="example"></a>Örnek  
  
```  
// xml_c_tag.cpp  
// compile with: /doc /LD  
// post-build command: xdcmake xml_c_tag.xdc  
  
/// Text for class MyClass.  
class MyClass {  
public:  
   int m_i;  
   MyClass() : m_i(0) {}  
  
   /// <summary><c>MyMethod</c> is a method in the <c>MyClass</c> class.  
   /// </summary>  
   int MyMethod(MyClass * a) {  
      return a -> m_i;  
   }  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML belgeleri](../ide/xml-documentation-visual-cpp.md)