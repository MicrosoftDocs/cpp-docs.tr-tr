---
title: /HEAP
description: MSVC bağlayıcı veya EDITBIN/HEAP seçeneği toplam yığın boyutunu ve isteğe bağlı olarak ek yığın bloklarının boyutunu ayarlar.
ms.date: 07/07/2020
f1_keywords:
- /heap
helpviewer_keywords:
- heap allocation, setting heap size
- HEAP editbin option
- -HEAP editbin option
- /HEAP editbin option
ms.assetid: 6ce759b5-75b7-44ff-a5fd-3a83a0ba9a48
ms.openlocfilehash: 7976ae2927ca731c83fa42e87da182fee4df3d7c
ms.sourcegitcommit: e17cc8a478b51739d67304d7d82422967b35f716
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/08/2020
ms.locfileid: "86127838"
---
# `/HEAP`

Yığının boyutunu bayt cinsinden ayarlar. Bu seçenek yalnızca yürütülebilir dosyalar için geçerlidir.

## <a name="syntax"></a>Sözdizimi

> **`/HEAP:`**_`reserve`_\[**`,`**_`commit`_]

## <a name="remarks"></a>Açıklamalar

*`reserve`* Bağımsız değişkeni, sanal bellekteki toplam ilk yığın ayırmayı belirtir. **`/HEAP`** Bağlayıcı veya [editbin](editbin-reference.md) seçeneği belirtilen değeri 4 baytlık en yakın katına yuvarlar. Varsayılan olarak, yığın boyutu 1 MB 'tır.

İsteğe bağlı *`commit`* bağımsız değişken, işletim sistemi tarafından yorumlamayı tabidir. Bir Windows işletim sisteminde, ayrılacak ilk fiziksel bellek miktarını belirtir. Yığın genişletildiğinde ne kadar daha fazla bellek ayrılacağını de belirtir. Yürütülen sanal bellek, disk belleği dosyasında ayrılan alanın ayrılmasına neden olur. Daha yüksek bir *`commit`* değer, uygulama daha fazla yığın alanı gerektiren, ancak bellek gereksinimlerini ve uygulama başlatma süresini arttığında sistemin daha az bellek ayırmasına izin verir. *`commit`* Değer değere eşit veya ondan küçük olmalıdır *`reserve`* . Varsayılan değer 4 KB 'tır.

*`reserve`* Ve *`commit`* değerlerini ondalık, C dilinde onaltılık veya sekizlik gösterimde belirtin. Örneğin, 1 MB değeri, ondalık olarak 1048576 olarak ya da onaltılı olarak 0x100000 veya sekizli olarak 04000000 olarak belirtilebilir. Varsayılan değerler, seçeneğiyle eşdeğerdir **`/HEAP:1048576,4096`** .

### <a name="example"></a>Örnek

Bu örnek bağlantı komutu, 2 MB yığın ayrılmış bir çalıştırılabilir *main.exe* oluşturur. İlk yığın ve sonraki yığın genişletmeleri 64 KB 'lik bloklar halinde gelir:

**`link /heap:0x200000,0x10000 main.obj`**

### <a name="to-set-this-linker-option-in-visual-studio"></a>Visual Studio 'da bu bağlayıcı seçeneğini ayarlamak için

1. Proje **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Yapılandırma özellikleri**  >  **bağlayıcı**  >  **sistem** özellik sayfasını seçin.

1. **Yığın ayırma boyutunu** ve **yığın kaydetme boyutu** özelliklerini ayarlayın, sonra değişikliklerinizi kaydetmek için **Tamam** ' ı veya **Uygula** ' yı seçin.

## <a name="see-also"></a>Ayrıca bkz.

[EDITBIN seçenekleri](editbin-options.md)\
[MSVC bağlayıcı seçenekleri](linker-options.md)
