---
title: Uzak derleme olayları (Linux C++)
ms.date: 06/07/2019
ms.assetid: 165d3690-5bd8-4b0b-bc66-8b699d85a61b
ms.openlocfilehash: 1e5c453da05fe65871fa7f6b0d4ca6528a96d4dd
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821484"
---
# <a name="build-event-properties-linux-c"></a>Derleme olay özellikleri (Linux C++)

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ile kullanılabilir ve üzerinde desteklenir.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="pre-build-event"></a>Derleme öncesi olay

Özellik | Açıklama
--- | ---
Komut satırı | Derleme öncesi olay aracının çalıştırması için bir komut satırı belirtir.
Açıklama | Derleme öncesi olay aracının görüntülemesi bir açıklama belirtir.
Derlemede kullan | Bu derleme olayının geçerli yapılandırmada derlemenin dışında tutulup tutulmayacağını belirtir.
Kopyalanacak ek dosyaları | Uzak sisteme kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak liste yerel için eşleme çiftlerine şunun gibi bir söz dizimi kullanılarak sağlanabilir: fulllocalpath1: = fullremotepath1; fulllocalpath2: = fulllocalpath2, burada bir yerel dosya kopyalanabilir uzak sistemde belirtilen uzak konuma.

## <a name="pre-link-event"></a>Bağlama öncesi olay

Özellik | Açıklama
--- | ---
Komut satırı | Bağlama öncesi olay aracının çalıştırması için bir komut satırı belirtir.
Açıklama | Bağlama öncesi olay aracının görüntülemesi bir açıklama belirtir.
Derlemede kullan | Bu derleme olayının geçerli yapılandırmada derlemenin dışında tutulup tutulmayacağını belirtir.
Kopyalanacak ek dosyaları | Uzak sisteme kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak liste yerel için eşleme çiftlerine şunun gibi bir söz dizimi kullanılarak sağlanabilir: fulllocalpath1: = fullremotepath1; fulllocalpath2: = fulllocalpath2, burada bir yerel dosya kopyalanabilir uzak sistemde belirtilen uzak konuma.

## <a name="post-build-event"></a>Derleme sonrası olay

Özellik | Açıklama
--- | ---
Komut satırı | Derleme sonrası olay aracının çalıştırması için bir komut satırı belirtir.
Açıklama | Derleme sonrası olay aracının görüntülemesi bir açıklama belirtir.
Derlemede kullan | Bu derleme olayının geçerli yapılandırmada derlemenin dışında tutulup tutulmayacağını belirtir.
Kopyalanacak ek dosyaları | Uzak sisteme kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak liste yerel için eşleme çiftlerine şunun gibi bir söz dizimi kullanılarak sağlanabilir: fulllocalpath1: = fullremotepath1; fulllocalpath2: = fulllocalpath2, burada bir yerel dosya kopyalanabilir uzak sistemde belirtilen uzak konuma.

## <a name="remote-pre-build-event"></a>Uzaktan derleme öncesi olay

Özellik | Açıklama
--- | ---
Komut satırı | Derleme öncesi olay aracının uzak sistemde çalıştırılması bir komut satırı belirtir.
Açıklama | Derleme öncesi olay aracının görüntülemesi bir açıklama belirtir.
Derlemede kullan | Bu derleme olayının geçerli yapılandırmada derlemenin dışında tutulup tutulmayacağını belirtir.
Kopyalanacak ek dosyaları | Uzak sistemden kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak liste olarak şunun gibi bir söz dizimi kullanılarak yerel eşleme çiftlerine için sağlanabilir: fullremotepath1: = fulllocalpath1; fulllocalpath2: = fulllocalpath2, burada bir uzak dosya kopyalanabilir yerel makinede belirtilen konuma.

## <a name="remote-pre-link-event"></a>Uzaktan bağlama öncesi olay

Özellik | Açıklama
--- | ---
Komut satırı | Bağlama öncesi olay aracının uzak sistemde çalıştırılması için bir komut satırı belirtir.
Açıklama | Bağlama öncesi olay aracının görüntülemesi bir açıklama belirtir.
Derlemede kullan | Bu derleme olayının geçerli yapılandırmada derlemenin dışında tutulup tutulmayacağını belirtir.
Kopyalanacak ek dosyaları | Uzak sistemden kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak liste olarak şunun gibi bir söz dizimi kullanılarak yerel eşleme çiftlerine için sağlanabilir: fullremotepath1: = fulllocalpath1; fulllocalpath2: = fulllocalpath2, burada bir uzak dosya kopyalanabilir yerel makinede belirtilen konuma.

## <a name="remote-post-build-event"></a>Uzaktan derleme sonrası olay

Özellik | Açıklama
--- | ---
Komut satırı | Derleme sonrası olay aracının uzak sistemde çalıştırılması için bir komut satırı belirtir.
Açıklama | Derleme sonrası olay aracının görüntülemesi bir açıklama belirtir.
Derlemede kullan | Bu derleme olayının geçerli yapılandırmada derlemenin dışında tutulup tutulmayacağını belirtir.
Kopyalanacak ek dosyaları | Uzak sistemden kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak liste olarak şunun gibi bir söz dizimi kullanılarak yerel eşleme çiftlerine için sağlanabilir: fullremotepath1: = fulllocalpath1; fulllocalpath2: = fulllocalpath2, burada bir uzak dosya kopyalanabilir yerel makinede belirtilen konuma.

::: moniker-end


