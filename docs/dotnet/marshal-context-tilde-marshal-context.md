---
title: 'marshal_context:: ~ marshal_context | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: reference
f1_keywords:
- marshal_context::~marshal_context
- msclr.interop.marshal_context.~marshal_context
- marshal_context.~marshal_context
- msclr::interop::marshal_context::~marshal_context
- ~marshal_context
dev_langs:
- C++
helpviewer_keywords:
- marshal_context class [C++], operations
ms.assetid: 34c41b38-4c33-4f61-b74e-831ac46b4ab5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: a6cb7ed3c7b1ee5b28c4943d83b6a8ca6166b6d0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33138094"
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
 [marshal_context Class](../dotnet/marshal-context-class.md)