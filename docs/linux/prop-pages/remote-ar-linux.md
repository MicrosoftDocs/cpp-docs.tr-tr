---
title: Uzak arşivi özellikleri (C++ Linux)
ms.date: 06/07/2019
ms.assetid: 5ee1e44c-8337-4c3a-b2f3-35e4be954f9f
f1_keywords: []
ms.openlocfilehash: 00de4ac56a9ce390672019c7fe5a838367823100
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821272"
---
# <a name="remote-archive-properties-c-linux"></a>Uzak arşivi özellikleri (C++ Linux)

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ile kullanılabilir ve üzerinde desteklenir.

::: moniker-end

::: moniker range=">=vs-2017"

Özellik | Açıklama
--- | ---
Arşiv dizini oluştur | Arşiv dizini (ranlib tarafından yapıldığı şekilde) oluşturun. Bu seçenek, bağlamayı hızlandırabilir ve kendi kitaplığındaki bağımlılığı azaltabilir.
Kısa arşiv oluştur | Bir arşiv oluşturun.  Bir arşiv, nesneleri katıştırmak yerine nesneleri için göreli yolları içerir.  İnce ve Normal arasında geçiş yapma varolan kitaplığın silinmesini gerektirir.
Herhangi bir uyarı oluştur | İse veya kitaplık oluşturulduğunda uyarı vermez.
Zaman damgasını çıkar | Zaman damgaları ve uid'ler/gid'ler için sıfır kullanın.
Başlangıç başlığını gösterme | Sürüm numarasını gösterme.
Ayrıntılı | Ayrıntılı
Ek Seçenekler | Ek Seçenekler.
Çıkış dosyası | / Out seçeneği varsayılan adını ve lib oluşturduğu program konumunu geçersiz kılar.
Arşivleyicide | Statik nesneler ya da uzak sistemdeki arşivleyicinin yolunu bağlama sırasında çağrılacak programı belirtir.
Arşivleyicide zaman aşımı | Uzak arşivleyicide zaman aşımı, milisaniye cinsinden.
Çıkışı Kopyala | Derleme çıkışı dosyasının Uzak sistemden yerel makineye kopyalanıp kopyalanmayacağını belirtir.

::: moniker-end
