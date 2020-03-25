---
title: Ayrılmış sözcükler
ms.date: 11/04/2016
f1_keywords:
- code
- CONFORMING
- DISCARDABLE
- Description
- base
- APPLOADER
- Data
- DYNAMIC
- DEV386
helpviewer_keywords:
- .def files [C++], reserved words
- def files [C++], reserved words
- linker [C++], reserved words
- reserved words [C++]
ms.assetid: 9b9f49e5-0739-45ab-a37e-81e3915ceb25
ms.openlocfilehash: 16caacb77e052eebc8e2cd101990ee373535bd6e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80171157"
---
# <a name="reserved-words"></a>Ayrılmış sözcükler

Aşağıdaki sözcükler bağlayıcı tarafından ayrılmıştır. Bu adlar, yalnızca ad çift tırnak işareti ("") içine alınsa, [modül tanımı deyimlerinde](module-definition-dot-def-files.md) bağımsız değişken olarak kullanılabilir.

||||
|-|-|-|
|**AppLoader**<sup>1</sup>|**InitInstance**<sup>2</sup>|**PRELOAD**|
|**TEMEL**|**IOPL**|**ÖZELLEŞTIRME**|
|**KODUDUR**|**Kitaplık**<sup>1</sup>|**PROTMODE**<sup>2</sup>|
|**UYGUN**|**LOADONCALL**<sup>1</sup>|**Saf**<sup>1</sup>|
|**VERILERI**|**Longnames**<sup>2</sup>|**ÖZELLIĞININ**|
|**AÇıKLAMASı**|**Taşınabilir**<sup>1</sup>|**READWRITE**|
|**DEV386**|**Taşınabilir**<sup>1</sup>|**Realmode**<sup>1</sup>|
|**DISCARDABLE**|**Çoklu**|**KALAN**|
|**TIR**|**ADA**|**Resdentname**<sup>1</sup>|
|**YALNıZCA YÜRÜTME**|**Newfiles**<sup>2</sup>|**BAŞLıKLı**|
|**Yalnızca Execute**|**NoData**<sup>1</sup>|**LARDA**|
|**EXECUTEREAD**|**Noıopl**<sup>1</sup>|**PAYLAŞıLAN**|
|**EXETYPE**|**NONAME**|**SUNUCULU**|
|**EXPORTS**|**Uyumsuz**<sup>1</sup>|**STACKSIZE**|
|**FIXED**<sup>1</sup> düzeltildi|**NONDISCARDABLE**|**STUB**|
|**İşlevler**<sup>2</sup>|**SEÇIM**|**Sürüm**|
|**HEAPSIZE**|**PAYLAŞıLMAYAN**|**WINDOWAPı**|
|**IŞLEMLERININ**|**Notwindowcompat**<sup>1</sup>|**WINDOWCOMPAT**|
|**Impure**<sup>1</sup>|**NESNEYI**|**PENCERELERIN**|
|**Dahil**<sup>2</sup>|**Eski**<sup>1</sup>||

<sup>1</sup> bağlayıcı bu terimle karşılaştığında bir uyarı ("yoksayıldı") yayar. Ancak, sözcük hala ayrıldı.

<sup>2</sup> bağlayıcı bu sözcüğü yoksayar, ancak hiçbir uyarı yayar.

## <a name="see-also"></a>Ayrıca bkz.

- [MSVC bağlayıcı başvurusu](linking.md)
- [MSVC Bağlayıcı Seçenekleri](linker-options.md)
