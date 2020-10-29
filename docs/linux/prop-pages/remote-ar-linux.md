---
title: Uzak Arşiv özellikleri (C++ Linux)
ms.date: 06/07/2019
ms.assetid: 5ee1e44c-8337-4c3a-b2f3-35e4be954f9f
f1_keywords: []
ms.openlocfilehash: 9e35c9cc0b8a99e87654f1052e8666c52e35a071
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/29/2020
ms.locfileid: "92924457"
---
# <a name="remote-archive-properties-c-linux"></a>Uzak Arşiv özellikleri (C++ Linux)

::: moniker range="msvc-140"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range=">=msvc-150"

| Özellik | Açıklama |
|--|--|
| Arşiv dizini oluştur | Arşiv dizini oluşturun (ranlib tarafından yapıldığı gibi). Bu seçenek, bağlamayı hızlandırabilir ve kendi kitaplığı içinde bağımlılığı azaltabilir. |
| Ince Arşiv oluştur | İnce Arşiv oluşturun.  İnce bir arşiv nesneleri katıştırmak yerine nesnelere göreli yollar içerir.  Ince ve normal arasında geçiş yapmak için var olan kitaplığın silinmesi gerekir. |
| Oluşturma sırasında uyarı yok | Kitaplık oluşturulduğunda ya da, uyarı vermez. |
| Kesme zaman damgası | Zaman damgaları ve uid 'ler/GID 'ler için sıfır kullanın. |
| Başlangıç başlığını gösterme | Sürüm numarasını gösterme. |
| Ayrıntılı | Ayrıntılı |
| Ek Seçenekler | Ek seçenekler. |
| Çıkış dosyası | /OUT seçeneği, LIB 'in oluşturduğu programın varsayılan adını ve konumunu geçersiz kılar. |
| Arşivleyicide | Statik nesnelerin bağlanması sırasında çağrılacak programı ya da uzak sistemdeki arşivleyicide yolunu belirtir. |
| Arşivleyicide zaman aşımı | Milisaniye cinsinden uzak arşivleyicide zaman aşımı. |
| Çıkışı Kopyala | Derleme çıkış dosyasının uzak sistemden yerel makineye kopyalanıp kopyalanmayacağını belirtir. |

::: moniker-end
