---
title: Uzak Arşiv özellikleri (C++ Linux)
ms.date: 06/07/2019
ms.assetid: 5ee1e44c-8337-4c3a-b2f3-35e4be954f9f
f1_keywords: []
ms.openlocfilehash: dc20eecef9947581ca87b9489285bc058a249e26
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446819"
---
# <a name="remote-archive-properties-c-linux"></a>Uzak Arşiv özellikleri (C++ Linux)

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

| Özellik | Açıklama |
|--|--|
| Arşiv dizini oluştur | Arşiv dizini oluşturun (ranlib tarafından yapıldığı gibi). Bu seçenek, bağlamayı hızlandırabilir ve kendi kitaplığı içinde bağımlılığı azaltabilir. |
| Ince Arşiv oluştur | İnce Arşiv oluşturun.  İnce bir arşiv nesneleri katıştırmak yerine nesnelere göreli yollar içerir.  Ince ve normal arasında geçiş yapmak için var olan kitaplığın silinmesi gerekir. |
| Oluşturma sırasında uyarı yok | Kitaplık oluşturulduğunda ya da, uyarı vermez. |
| Kesme zaman damgası | Zaman damgaları ve uid 'ler/GID 'ler için sıfır kullanın. |
| Başlangıç başlığını gösterme | Sürüm numarasını gösterme. |
| Ayrıntılı | Ayrıntılı |
| Ek Seçenekler | Ek seçenekler. |
| Çıkış Dosyası | /OUT seçeneği, LIB 'in oluşturduğu programın varsayılan adını ve konumunu geçersiz kılar. |
| Arşivleyicide | Statik nesnelerin bağlanması sırasında çağrılacak programı ya da uzak sistemdeki arşivleyicide yolunu belirtir. |
| Arşivleyicide zaman aşımı | Milisaniye cinsinden uzak arşivleyicide zaman aşımı. |
| Çıkışı Kopyala | Derleme çıkış dosyasının uzak sistemden yerel makineye kopyalanıp kopyalanmayacağını belirtir. |

::: moniker-end
