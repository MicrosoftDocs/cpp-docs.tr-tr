---
title: ExitInstance Üye İşlevi
ms.date: 11/04/2016
f1_keywords: []
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
ms.openlocfilehash: b1c5b3a20f25f909188023ab1650bc41316d7a9f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637742"
---
# <a name="exitinstance-member-function"></a>ExitInstance Üye İşlevi

[ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) sınıfının üye işlevinde [CWinApp](../mfc/reference/cwinapp-class.md) uygulamanızı bir kopyasını sonlandırır, genellikle bir kullanıcı uygulamadan çıkmayı sonucu olarak her zaman çağrılır.

Geçersiz kılma `ExitInstance` grafik cihaz arabirimi (GDI) kaynakları serbest bırakma veya program yürütme sırasında kullanılan belleğini gibi özel bir temizleme işlemi gerekiyorsa. Belgeler ve görünümler gibi standart öğelerinin temizleme, ancak bu nesnelere belirli özel temizleme yapmak için başka geçersiz kılınabilir işlevler ile framework tarafından sağlanır.

## <a name="see-also"></a>Ayrıca Bkz.

[CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
