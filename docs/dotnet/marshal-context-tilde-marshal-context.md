---
title: 'marshal_context:: ~ marshal_context | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- marshal_context::~marshal_context
- msclr.interop.marshal_context.~marshal_context
- marshal_context.~marshal_context
- msclr::interop::marshal_context::~marshal_context
- ~marshal_context
dev_langs: C++
helpviewer_keywords: marshal_context class [C++], operations
ms.assetid: 34c41b38-4c33-4f61-b74e-831ac46b4ab5
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: cb052c27888bf168206c80fc06edd24034880433
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="marshalcontextmarshalcontext"></a>marshal_context::~marshal_context
Bozar bir `marshal_context` nesnesi.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
~marshal_context();  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Bazı veri dönüşümleri sıralama bağlamı gerektirir. Bkz: [, genel bakış hazırlama c++](../dotnet/overview-of-marshaling-in-cpp.md) hangi çevirileri bir bağlam gerektirir ve uygulamanızda dahil edilecek hazırlama hangi dosya sahip hakkında daha fazla bilgi.  
  
 Silme bir `marshal_context` o bağlam tarafından dönüştürülen bir veri nesnesi geçersiz kılacak. Sonra verilerinizi korumak istiyorsanız bir `marshal_context` nesnesi yok, veriler korunur bir değişkene el ile kopyalamanız gerekir.  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi dosyası:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, veya \<msclr\marshal_atl.h >  
  
 **Namespace:** msclr::interop  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++'da hazırlamaya genel bakış](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_as](../dotnet/marshal-as.md)   
 [marshal_context sınıfı](../dotnet/marshal-context-class.md)