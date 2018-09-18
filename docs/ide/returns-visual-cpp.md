---
title: '&lt;döndürür&gt; (Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- returns
- <returns>
dev_langs:
- C++
helpviewer_keywords:
- returns C++ XML tag
- <returns> C++ XML tag
ms.assetid: 5e3b0ed9-838d-4953-a93e-76d2d0a19fb9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed871ee2148b6b731ab9354cd45c2e178b4d85a8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46056085"
---
# <a name="ltreturnsgt-visual-c"></a>&lt;döndürür&gt; (Visual C++)
\<Döndürür > etiketi yöntemi bildirimi için açıklama dönüş değeri tanımlamak için kullanılmalıdır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<returns>description</returns>  
```  
  
#### <a name="parameters"></a>Parametreler  
*Açıklaması*<br/>
Dönüş değeri bir açıklaması.  
  
## <a name="remarks"></a>Açıklamalar  
 Derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.  
  
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
 [XML Belgeleri](../ide/xml-documentation-visual-cpp.md)