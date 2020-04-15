---
title: Uzaktan Arşiv Özellikleri (C++ Linux)
ms.date: 06/07/2019
ms.assetid: 5ee1e44c-8337-4c3a-b2f3-35e4be954f9f
f1_keywords: []
ms.openlocfilehash: 3b6f71d9cceccf0b0221be46bacb1294d84533cd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364297"
---
# <a name="remote-archive-properties-c-linux"></a>Uzaktan Arşiv Özellikleri (C++ Linux)

::: moniker range="vs-2015"

Linux desteği Visual Studio 2017 ve sonrası sürümlerinde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

| Özellik | Açıklama |
|--|--|
| Arşiv dizini oluşturma | Bir arşiv dizini oluşturun (ranlib tarafından yapıldığı gibi). Bu seçenek, bağlamayı hızlandırabilir ve kendi kitaplığı içindeki bağımlılığı azaltabilir. |
| İnce Arşiv Oluştur | İnce bir arşiv oluşturun.  İnce bir arşiv, nesneleri katıştırmak yerine nesnelere göreli yollar içerir.  İnce ve Normal arasında geçiş yapmak için varolan kitaplığın silmesi gerekir. |
| Oluştur'da Uyarı Yok | Kitaplığın oluşturulduğu veya oluşturulduğu konusunda uyarmaz. |
| Budanma Zaman Damgası | Zaman damgaları ve uids/gids için sıfır kullanın. |
| Başlangıç Banner'ı bastır | Sürüm numarasını gösterme. |
| Ayrıntılı | Ayrıntılı |
| Ek Seçenekler | Ek seçenekler. |
| Çıktı Dosyası | /OUT seçeneği, lib'in oluşturduğu programın varsayılan adını ve konumunu geçersiz kılar. |
| Arşiv | Statik nesnelerin bağlanması sırasında çağırmak için program veya uzak sistemde arşivleyici yolu belirtir. |
| Arşivleyici Zaman Astarı | Uzak arşivleyici zaman, milisaniye cinsinden. |
| Çıktıyı Kopyala | Yapı çıktısı dosyasının uzak sistemden yerel makineye kopyalanıp kopyalanmayacağını belirtir. |

::: moniker-end
