---
title: '&lt;verir&gt; (Visual C++) | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- returns
- <returns>
dev_langs: C++
helpviewer_keywords:
- returns C++ XML tag
- <returns> C++ XML tag
ms.assetid: 5e3b0ed9-838d-4953-a93e-76d2d0a19fb9
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: babb15cd887ddd877d2aa898b9df7d35618be990
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ltreturnsgt-visual-c"></a>&lt;verir&gt; (Visual C++)
\<Döndürür > etiketi açıklamasında bir yöntem bildirimi için dönüş değerini açıklamak için kullanılmalıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `description`  
 Dönüş değeri açıklaması.  
  
## <a name="remarks"></a>Açıklamalar  
 İle derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) bir dosyaya işlem belgesi açıklamaları için.  
  
## <a name="example"></a>Örnek  
  
```  
// xml_returns_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_returns_tag.dll  
  
/// Text for class MyClass.  
public ref class MyClass {  
public:  
   /// <returns>Returns zero.</returns>  
   int GetZero() { return 0; }  
};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML belgeleri](../ide/xml-documentation-visual-cpp.md)