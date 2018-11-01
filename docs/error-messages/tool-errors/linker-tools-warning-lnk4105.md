---
title: Bağlayıcı Araçları Uyarısı LNK4105
ms.date: 11/04/2016
f1_keywords:
- LNK4105
helpviewer_keywords:
- LNK4105
ms.assetid: 6c7bebf4-4ea6-4533-a6ed-e563d43abbd7
ms.openlocfilehash: 880c8519a530f492d0c322575a1386af8a7d0187
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475601"
---
# <a name="linker-tools-warning-lnk4105"></a>Bağlayıcı Araçları Uyarısı LNK4105

'seçeneği'; seçeneği ile belirtilen hiçbir bağımsız değişken seçeneği yoksayılıyor

Bu uyarı yalnızca oluşur, [/Libpath](../../build/reference/libpath-additional-libpath.md) seçeneği ayarlanır. Bu seçeneği ile hiçbir dizin belirtilirse, bağlayıcı seçeneğini yoksayar ve bu uyarı iletisi oluşturur.

Mevcut ortam kitaplık ayarları geçersiz kılmak gerekmiyorsa/Libpath seçenek bağlayıcı komut satırından kaldırın. Alternatif arama yolu kitaplıkları için kullanmak istiyorsanız, / Libpath seçeneği aşağıdaki alternatif yolu belirtin.

## <a name="example"></a>Örnek

```
link /libpath:c:\filepath\lib bar.obj
```

gerekli kitaplıkları aramak için bağlayıcı yönlendirmelisiniz `c:\filepath\lib` varsayılan konumlarda arama önce.