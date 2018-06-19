---
title: ExitInstance üye işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords: []
dev_langs:
- C++
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 954d2248061ec571d9d2ba8804c1f7c97275cbfc
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343505"
---
# <a name="exitinstance-member-function"></a>ExitInstance Üye İşlevi
[ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) sınıfının üye işlevini [CWinApp](../mfc/reference/cwinapp-class.md) uygulamanız bir kopyasını sonlandırır, genellikle uygulama çıkma kullanıcı sonucunda her zaman çağrılır.  
  
 Geçersiz kılma `ExitInstance` grafik cihaz arabirimi (GDI) kaynakları serbest bırakma veya program yürütülmesi sırasında kullanılan bellek ayırmayı kaldırma gibi özel temizleme işleme ihtiyacınız varsa. Belgeler ve görünümler gibi standart öğelerinin temizleme ancak, bu nesnelerle belirli özel temizleme yapmak için diğer geçersiz kılınabilir işlevlerle framework tarafından sağlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
