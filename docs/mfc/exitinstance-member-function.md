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
ms.openlocfilehash: da411fbecdea0a1e7b8976ca119057204693a9bd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46387867"
---
# <a name="exitinstance-member-function"></a>ExitInstance Üye İşlevi

[ExitInstance](../mfc/reference/cwinapp-class.md#exitinstance) sınıfının üye işlevinde [CWinApp](../mfc/reference/cwinapp-class.md) uygulamanızı bir kopyasını sonlandırır, genellikle bir kullanıcı uygulamadan çıkmayı sonucu olarak her zaman çağrılır.

Geçersiz kılma `ExitInstance` grafik cihaz arabirimi (GDI) kaynakları serbest bırakma veya program yürütme sırasında kullanılan belleğini gibi özel bir temizleme işlemi gerekiyorsa. Belgeler ve görünümler gibi standart öğelerinin temizleme, ancak bu nesnelere belirli özel temizleme yapmak için başka geçersiz kılınabilir işlevler ile framework tarafından sağlanır.

## <a name="see-also"></a>Ayrıca Bkz.

[CWinApp: Uygulama Sınıfı](../mfc/cwinapp-the-application-class.md)
