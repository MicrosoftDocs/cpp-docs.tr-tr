---
title: Kendi yardımcı işlevinizi geliştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- helper functions
ms.assetid: a845429d-68b1-4e14-aa88-f3f5343bd490
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e6b8e397fecc8f14140cd7c86217421d5aa1a749
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
---
# <a name="developing-your-own-helper-function"></a>Kendi Yardımcı İşlevinizi Geliştirme
DLL veya içeri aktarmalar adlarına göre belirli işlemini yapmak için yordamının kendi sürüm sağlamak isteyebilirsiniz. Bunu yapmanın iki yöntemi vardır: büyük olasılıkla sağlanan kodu göre kendi kodlama veya yalnızca daha önce ayrıntılı bildirim kancaları kullanarak sağlanan sürüm takma.  
  
 Kendi kod  
 Bu, aslında girilen kod kılavuz olarak yenisi için kullanabileceğiniz beri oldukça basittir. Elbette, çağırma kurallarına uyması gerekir ve bağlayıcı oluşturulan dönüştürücüler döndürürse, uygun işlev işaretçisi döndürmesi gerekir. Bir kez kodunuzda oldukça çok çağrı karşılamak ya da dışında çağrı almak amacıyla istediğiniz yapabilirsiniz.  
  
 Bildirim kanca işleme başlangıç kullanın  
 Büyük olasılıkla yalnızca bildirim dliStartProcessing üzerinde varsayılan Yardımcısı aynı değerleri alan bir kullanıcı tarafından sağlanan bildirim kanca işlevi için yeni bir işaretçi sağlamak kolay olacaktır. Bu noktada, başarılı bir geri döndürme varsayılan Yardımcısı için varsayılan yardımcı tüm işlenmesi atlayacaktır gibi kanca işlevini temelde yeni yardımcı işlevini olabilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Gecikmeli Yüklenen DLL'ler için Bağlayıcı Desteği](../../build/reference/linker-support-for-delay-loaded-dlls.md)