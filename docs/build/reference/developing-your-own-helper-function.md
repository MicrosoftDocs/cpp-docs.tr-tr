---
title: "Kendi yardımcı işlevinizi geliştirme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: helper functions
ms.assetid: a845429d-68b1-4e14-aa88-f3f5343bd490
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 3a2683fbc259cbac3551840f9ebe6e7c651430bc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="developing-your-own-helper-function"></a>Kendi Yardımcı İşlevinizi Geliştirme
DLL veya içeri aktarmalar adlarına göre belirli işlemini yapmak için yordamının kendi sürüm sağlamak isteyebilirsiniz. Bunu yapmanın iki yöntemi vardır: büyük olasılıkla sağlanan kodu göre kendi kodlama veya yalnızca daha önce ayrıntılı bildirim kancaları kullanarak sağlanan sürüm takma.  
  
 Kendi kod  
 Bu, aslında girilen kod kılavuz olarak yenisi için kullanabileceğiniz beri oldukça basittir. Elbette, çağırma kurallarına uyması gerekir ve bağlayıcı oluşturulan dönüştürücüler döndürürse, uygun işlev işaretçisi döndürmesi gerekir. Bir kez kodunuzda oldukça çok çağrı karşılamak ya da dışında çağrı almak amacıyla istediğiniz yapabilirsiniz.  
  
 Bildirim kanca işleme başlangıç kullanın  
 Büyük olasılıkla yalnızca bildirim dliStartProcessing üzerinde varsayılan Yardımcısı aynı değerleri alan bir kullanıcı tarafından sağlanan bildirim kanca işlevi için yeni bir işaretçi sağlamak kolay olacaktır. Bu noktada, başarılı bir geri döndürme varsayılan Yardımcısı için varsayılan yardımcı tüm işlenmesi atlayacaktır gibi kanca işlevini temelde yeni yardımcı işlevini olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gecikmeli yüklenen DLL'ler için bağlayıcı desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md)