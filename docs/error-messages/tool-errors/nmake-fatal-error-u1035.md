---
title: NMAKE Önemli Hatası U1035
ms.date: 11/04/2016
f1_keywords:
- U1035
helpviewer_keywords:
- U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
ms.openlocfilehash: 3eda424574dfa48901cf4dc6aea3b28beb739dc0
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80193725"
---
# <a name="nmake-fatal-error-u1035"></a>NMAKE Önemli Hatası U1035

sözdizimi hatası: ': ' veya ' = ' ayırıcısı bekleniyor

İki nokta üst üste ( **:** ) veya eşittir işareti ( **=** ) bekleniyordu.

### <a name="to-fix-by-checking-the-following-possible-causes"></a>Aşağıdaki olası nedenleri denetleyerek onarmak için

1. İki nokta üst üste bir hedefi izmedi.

1. İki nokta üst üste ve boşluk (örneğin:) Tek harflik bir hedef izlenir. NMAKE onu bir sürücü belirtimi olarak yorumlanmış.

1. İki nokta üst üste bir çıkarım kuralı izmedi.

1. Makro tanımının ardından eşittir işareti yoktu.

1. Bir karakter, bir komutun yeni bir satıra devam etmesi için kullanılan bir ters eğik çizgi ( **\\** ) izler.

1. Hiçbir NMAKE sözdizimi kuralını izlemeyen bir dize görüntülendi.

1. Derleme görevleri dosyası bir sözcük işlemcisi tarafından biçimlendirildi.
