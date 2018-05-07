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
ms.openlocfilehash: 380a2c27a761154e59826259d3e1e682ae7fbd87
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="ltremarksgt-visual-c"></a>&lt;Açıklamalar&gt; (Visual C++)
\<Açıklamalar > etiketi bir türü hakkında bilgi eklemek için kullanılır, bilgileri ekleme ile belirtilen [ \<Özet >](../ide/summary-visual-cpp.md). Bu bilgiler görüntülenir [Nesne Tarayıcısı](http://msdn.microsoft.com/en-us/f89acfc5-1152-413d-9f56-3dc16e3f0470) ve kod açıklama Web raporu.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
<remarks>description</remarks>  
```  
  
#### <a name="parameters"></a>Parametreler  
 `description`  
 Üye açıklaması.  
  
## <a name="remarks"></a>Açıklamalar  
 İle derleme [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) bir dosyaya işlem belgesi açıklamaları için.  
  
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