---
title: "ExitInstance üye işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: 
dev_langs: C++
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 99898a5e80c3f487c7f53fe81d13d3d1eb55ebd5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="exitinstance-member-function"></a>ExitInstance Üye İşlevi
[ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) sınıfının üye işlevini [CWinApp](../mfc/reference/cwinapp-class.md) uygulamanız bir kopyasını sonlandırır, genellikle uygulama çıkma kullanıcı sonucunda her zaman çağrılır.  
  
 Geçersiz kılma `ExitInstance` grafik cihaz arabirimi (GDI) kaynakları serbest bırakma veya program yürütülmesi sırasında kullanılan bellek ayırmayı kaldırma gibi özel temizleme işleme ihtiyacınız varsa. Belgeler ve görünümler gibi standart öğelerinin temizleme ancak, bu nesnelerle belirli özel temizleme yapmak için diğer geçersiz kılınabilir işlevlerle framework tarafından sağlanır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
