---
title: "marshal_context sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: marshal_context
dev_langs: C++
helpviewer_keywords: marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9b59dfa82563a0c115f521bb881411981a30efc9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="marshalcontext-class"></a>marshal_context Sınıfı
Bu sınıf, yerel ve yönetilen ortamlar arasında veri dönüştürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class marshal_context  
```  
  
## <a name="remarks"></a>Açıklamalar  
 Kullanım `marshal_context` bir bağlam gerektiren veri dönüşümleri için sınıf. Bkz: [, genel bakış hazırlama c++](../dotnet/overview-of-marshaling-in-cpp.md) bir bağlam hangi dönüşümleri gerektirir ve dahil edilecek hazırlama hangi dosya sahip hakkında daha fazla bilgi. Bir bağlam kullandığınızda hazırlama sonucunu yalnızca geçerliliğinin `marshal_context` nesne yok. Sonuç kümenizi korumak için verileri kopyalamanız gerekir.  
  
 Aynı `marshal_context` birden çok veri dönüştürmeleri için kullanılabilir. Bu şekilde bağlamda yeniden önceki hazırlama çağrıları sonuçlarından etkilemez.  
  
## <a name="requirements"></a>Gereksinimler  
 **Üstbilgi dosyası:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, veya \<msclr\marshal_atl.h >  
  
 **Namespace:** msclr::interop  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [C++'da hazırlamaya genel bakış](../dotnet/overview-of-marshaling-in-cpp.md)   
 [marshal_as](../dotnet/marshal-as.md)