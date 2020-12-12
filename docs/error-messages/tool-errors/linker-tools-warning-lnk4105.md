---
description: 'Daha fazla bilgi edinin: bağlayıcı araçları uyarısı LNK4105'
title: Bağlayıcı Araçları Uyarısı LNK4105
ms.date: 11/04/2016
f1_keywords:
- LNK4105
helpviewer_keywords:
- LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
ms.openlocfilehash: 6536273a0b3e5b6e60b782e5953a70a7b3eb2798
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294424"
---
# <a name="linker-tools-warning-lnk4105"></a>Bağlayıcı Araçları Uyarısı LNK4105

' OPTION ' seçeneği ile hiçbir bağımsız değişken belirtilmedi; seçenek yoksayılıyor

Bu uyarı yalnızca [/LIBPATH](../../build/reference/libpath-additional-libpath.md) seçeneği ayarlandığında oluşur. Bu seçenekle bir dizin belirtilmemişse, bağlayıcı seçeneği yoksayar ve bu uyarı iletisini oluşturur.

Mevcut çevresel kitaplık ayarlarını geçersiz kılmanız gerekmiyorsa,/LIBPATH seçeneğini bağlayıcı komut satırından kaldırın. Kitaplıklar için alternatif bir arama yolu kullanmak istiyorsanız,/LıBPATH seçeneğini izleyerek alternatif yolu belirtin.

## <a name="example"></a>Örnek

```
link /libpath:c:\filepath\lib bar.obj
```

, `c:\filepath\lib` varsayılan konumlarda arama yapmadan önce içinde gerekli kitaplıkları aramak için bağlayıcı yönlendirir.
