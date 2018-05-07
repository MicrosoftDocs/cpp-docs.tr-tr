---
title: Dinamik Nesne oluşturma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5763e3f0f3ee5a0e58ac20fe9f637e4f7e097999
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="dynamic-object-creation"></a>Dinamik Nesne Oluşturma
Bu makalede, bir nesne çalışma zamanında dinamik olarak oluşturmak açıklanmaktadır. Yordam çalışma zamanı sınıf bilgileri makalesinde açıklandığı gibi kullanır [çalışma zamanı sınıf bilgilerine erişme](../mfc/accessing-run-time-class-information.md).  
  
#### <a name="to-dynamically-create-an-object-given-its-run-time-class"></a>Dinamik olarak, çalışma zamanı sınıf verildiğinde nesne oluşturmak için  
  
1.  Dinamik olarak kullanarak bir nesne oluşturmak için aşağıdaki kodu kullanın `CreateObject` işlevinin `CRuntimeClass`. Hatada, unutmayın `CreateObject` döndürür **NULL** yerine bir özel durum oluşturma:  
  
     [!code-cpp[NVC_MFCCObjectSample#6](../mfc/codesnippet/cpp/dynamic-object-creation_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject Kullanma](../mfc/using-cobject.md)

