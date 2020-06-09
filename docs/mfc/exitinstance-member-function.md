---
title: ExitInstance Üye İşlevi
ms.date: 11/04/2016
f1_keywords: []
helpviewer_keywords:
- programs [MFC], terminating
- CWinApp class [MFC], ExitInstance
- ExitInstance method [MFC]
ms.assetid: 5bb597bd-8dab-4d49-8bcf-9c45aa8be4a2
ms.openlocfilehash: 58546d26293ad48a39a36b98ba4bfdabb68385ee
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84622690"
---
# <a name="exitinstance-member-function"></a>ExitInstance Üye İşlevi

[CWinApp](reference/cwinapp-class.md) sınıfının [ExitInstance](reference/cwinapp-class.md#exitinstance) üye işlevi, uygulamanızın bir kopyası sonlandırıldığında, genellikle kullanıcının uygulamadan çıkma sonucu olarak çağrılır.

`ExitInstance`Grafik cihaz arabirimi (GDI) kaynaklarını serbest bırakma veya program yürütmesi sırasında kullanılan belleği ayırmayı kaldırma gibi özel temizleme işleme gerekiyorsa, geçersiz kılın. Ancak, belgeler ve görünümler gibi standart öğelerin temizlenmesi, bu nesnelere özgü özel temizlik yapmak için diğer geçersiz kılınabilir işlevlerle Framework tarafından sağlanır.

## <a name="see-also"></a>Ayrıca bkz.

[CWinApp: Uygulama Sınıfı](cwinapp-the-application-class.md)
