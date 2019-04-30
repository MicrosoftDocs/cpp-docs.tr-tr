---
title: ExitInstance Üye İşlevi
ms.date: 11/04/2016
f1_keywords: []
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
ms.openlocfilehash: c76f588b22ad8ffd1d3dae954c5113feffb62a3f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62405826"
---
# <a name="exitinstance-member-function"></a>ExitInstance Üye İşlevi

[ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) sınıfının üye işlevinde [CWinApp](../mfc/reference/cwinapp-class.md) uygulamanızı bir kopyasını sonlandırır, genellikle bir kullanıcı uygulamadan çıkmayı sonucu olarak her zaman çağrılır.

Geçersiz kılma `ExitInstance` grafik cihaz arabirimi (GDI) kaynakları serbest bırakma veya program yürütme sırasında kullanılan belleğini gibi özel bir temizleme işlemi gerekiyorsa. Belgeler ve görünümler gibi standart öğelerinin temizleme, ancak bu nesnelere belirli özel temizleme yapmak için başka geçersiz kılınabilir işlevler ile framework tarafından sağlanır.

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
