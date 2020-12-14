---
description: 'Daha fazla bilgi edinin: ExitInstance üye Işlevi'
title: ExitInstance Üye İşlevi
ms.date: 11/04/2016
f1_keywords: []
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
ms.openlocfilehash: a469d29c6b8dc2b822928293ee3bd083ccce95e7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314730"
---
# <a name="exitinstance-member-function"></a>ExitInstance Üye İşlevi

[CWinApp](reference/cwinapp-class.md) sınıfının [ExitInstance](reference/cwinapp-class.md#exitinstance) üye işlevi, uygulamanızın bir kopyası sonlandırıldığında, genellikle kullanıcının uygulamadan çıkma sonucu olarak çağrılır.

`ExitInstance`Grafik cihaz arabirimi (GDI) kaynaklarını serbest bırakma veya program yürütmesi sırasında kullanılan belleği ayırmayı kaldırma gibi özel temizleme işleme gerekiyorsa, geçersiz kılın. Ancak, belgeler ve görünümler gibi standart öğelerin temizlenmesi, bu nesnelere özgü özel temizlik yapmak için diğer geçersiz kılınabilir işlevlerle Framework tarafından sağlanır.

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: uygulama sınıfı](cwinapp-the-application-class.md)
