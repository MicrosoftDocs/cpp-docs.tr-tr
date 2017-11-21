---
title: "Dinamik Nesne oluşturma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- object creation [MFC], dynamically at run time
- CObject class [MFC], dynamic object creation
- objects [MFC], creating dynamically at run time
- dynamic object creation [MFC]
ms.assetid: 3e0f51cb-3e24-4231-817f-1c0ce9f2d5df
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3ac2371e6f9e8a4ba351b482b50f347bee164e02
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="dynamic-object-creation"></a>Dinamik Nesne Oluşturma
Bu makalede, bir nesne çalışma zamanında dinamik olarak oluşturmak açıklanmaktadır. Yordam çalışma zamanı sınıf bilgileri makalesinde açıklandığı gibi kullanır [çalışma zamanı sınıf bilgilerine erişme](../mfc/accessing-run-time-class-information.md).  
  
#### <a name="to-dynamically-create-an-object-given-its-run-time-class"></a>Dinamik olarak, çalışma zamanı sınıf verildiğinde nesne oluşturmak için  
  
1.  Dinamik olarak kullanarak bir nesne oluşturmak için aşağıdaki kodu kullanın `CreateObject` işlevinin `CRuntimeClass`. Hatada, unutmayın `CreateObject` döndürür **NULL** yerine bir özel durum oluşturma:  
  
     [!code-cpp[NVC_MFCCObjectSample#6](../mfc/codesnippet/cpp/dynamic-object-creation_1.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject kullanma](../mfc/using-cobject.md)

