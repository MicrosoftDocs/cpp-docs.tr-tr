---
title: '&lt;Açıklamalar&gt; (Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- remarks
- <remarks>
dev_langs:
- C++
helpviewer_keywords:
- <remarks> C++ XML tag
- remarks C++ XML tag
ms.assetid: c820083b-3192-40ab-9ec8-1472c55b4247
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5bf60222b276050af5296d678985eda8fd12948b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027576"
---
# <a name="ltremarksgt-visual-c"></a>&lt;Açıklamalar&gt; (Visual C++)
\<Remarks > etiketi, bir tür hakkında bilgi eklemek için kullanılır, ek bilgiler ile belirtilen [ \<Özet >](../ide/summary-visual-cpp.md). Bu bilgileri görüntülenen [Nesne Tarayıcısı](/visualstudio/ide/viewing-the-structure-of-code) ve kod açıklaması Web raporu.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a>Parametreler  
*Açıklaması*<br/>
Üye açıklaması.  
  
## <a name="remarks"></a>Açıklamalar  
 Derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) işlem belgeleri açıklamaları için bir dosya için.  
  
## <a name="example"></a>Örnek  
  
```  
// xml_remarks_tag.cpp  
// compile with: /LD /clr /doc  
// post-build command: xdcmake xml_remarks_tag.dll  
  
using namespace System;  
  
/// <summary>  
/// You may have some primary information about this class.  
/// </summary>  
/// <remarks>  
/// You may have some additional information about this class.  
/// </remarks>  
public ref class MyClass {};  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [XML Belgeleri](../ide/xml-documentation-visual-cpp.md)