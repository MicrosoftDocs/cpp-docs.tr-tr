---
title: Bağlayıcı Araçları Uyarısı LNK4105
ms.date: 11/04/2016
f1_keywords:
- LNK4105
helpviewer_keywords:
- LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
ms.openlocfilehash: 655a6dfde77984cd0c941ec0d8abb0c4d099c80f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80183299"
---
# <a name="linker-tools-warning-lnk4105"></a>Bağlayıcı Araçları Uyarısı LNK4105

' OPTION ' seçeneği ile hiçbir bağımsız değişken belirtilmedi; seçenek yoksayılıyor

Bu uyarı yalnızca [/LIBPATH](../../build/reference/libpath-additional-libpath.md) seçeneği ayarlandığında oluşur. Bu seçenekle bir dizin belirtilmemişse, bağlayıcı seçeneği yoksayar ve bu uyarı iletisini oluşturur.

Mevcut çevresel kitaplık ayarlarını geçersiz kılmanız gerekmiyorsa,/LIBPATH seçeneğini bağlayıcı komut satırından kaldırın. Kitaplıklar için alternatif bir arama yolu kullanmak istiyorsanız,/LıBPATH seçeneğini izleyerek alternatif yolu belirtin.

## <a name="example"></a>Örnek

```
link /libpath:c:\filepath\lib bar.obj
```

, varsayılan konumlarda aramadan önce `c:\filepath\lib`, gerekli kitaplıkları aramak için bağlayıcı yönlendirir.
