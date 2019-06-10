---
title: Genel Özellikler (Linux C++ derleme görevleri dosyası projesi) | Microsoft Docs
ms.date: 06/07/2019
ms.assetid: 3dec6853-43f6-412b-9806-9bfad333a204
ms.openlocfilehash: a64066ad3c8d7e6ca8bfa9d3d82670ff1da4b527
ms.sourcegitcommit: 8adabe177d557c74566c13145196c11cef5d10d4
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66821449"
---
# <a name="makefile-project-properties-linux-c"></a>Derleme görevleri dosyası özellikleri (Linux C++)

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ile kullanılabilir ve üzerinde desteklenir.

::: moniker-end

::: moniker range=">=vs-2017"

Bu Linux Makefile projesi içinde mevcut olan özelliklerin kısmi bir listesidir. Çok sayıda derleme görevleri dosyası proje özellikleri için Linux C++ konsol uygulaması projesi özellikleri aynıdır.

## <a name="general"></a>Genel

Özellik | Açıklama | Seçenekleri
--- | ---| ---
Çıkış dizini | Çıkış dosyası dizinine göreli bir yol belirtir; ortam değişkenleri içerebilir.
Ara dizin | Ara dosya dizinine göreli bir yol belirtir; ortam değişkenleri içerebilir.
Derleme günlüğü dosyası | Günlük kaydı ne zaman oluşturulacağını yazılacak derleme günlüğü dosyasını belirtir.
Yapılandırma türü | Bu yapılandırmanın oluşturduğu çıkışın türünü belirtir. | **Dinamik kitaplık (.so)** -dinamik kitaplık (.so)<br>**Statik kitaplık (.a)** -statik kitaplık (.a)<br>**Uygulama (.out)** -uygulama (.out)<br>**Derleme görevleri dosyası** -derleme görevleri dosyası<br>
Uzaktan derleme makinesi | Dağıtma ve hata ayıklama hedef makine veya uzak derleme için kullanılacak cihaz.
Uzaktan derleme kök dizini | Uzak makine veya cihazdaki bir dizinin yolunu belirtir.
Uzaktan derleme proje dizini | Uzak makine veya cihaz projesi için bir dizinin yolunu belirtir.

## <a name="debugging"></a>Hata Ayıklama

Bkz: [hata ayıklayıcı, özellikleri (Linux C++)](debugging-linux.md)

## <a name="copy-sources"></a>Kaynakları Kopyala

Bkz: [kopyalama kaynakları proje özellikleri (Linux C++)](copy-sources-project.md).

## <a name="build-events"></a>Derleme olayları

### <a name="pre-build-event"></a>Derleme öncesi olay

Özellik | Açıklama
--- | ---
Komut satırı | Derleme öncesi olay aracının çalıştırması için bir komut satırı belirtir.
Açıklama | Derleme öncesi olay aracının görüntülemesi bir açıklama belirtir.
Derlemede kullan | Bu derleme olayının geçerli yapılandırmada derlemenin dışında tutulup tutulmayacağını belirtir.
Kopyalanacak ek dosyaları | Uzak sisteme kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak liste yerel için eşleme çiftlerine şunun gibi bir söz dizimi kullanılarak sağlanabilir: fulllocalpath1: = fullremotepath1; fulllocalpath2: = fulllocalpath2, burada bir yerel dosya kopyalanabilir uzak sistemde belirtilen uzak konuma.

### <a name="post-build-event"></a>Derleme sonrası olay

Özellik | Açıklama
--- | ---
Komut satırı | Derleme sonrası olay aracının çalıştırması için bir komut satırı belirtir.
Açıklama | Derleme sonrası olay aracının görüntülemesi bir açıklama belirtir.
Derlemede kullan | Bu derleme olayının geçerli yapılandırmada derlemenin dışında tutulup tutulmayacağını belirtir.
Kopyalanacak ek dosyaları | Uzak sisteme kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak liste yerel için eşleme çiftlerine şunun gibi bir söz dizimi kullanılarak sağlanabilir: fulllocalpath1: = fullremotepath1; fulllocalpath2: = fulllocalpath2, burada bir yerel dosya kopyalanabilir uzak sistemde belirtilen uzak konuma.

### <a name="remote-pre-build-event"></a>Uzaktan derleme öncesi olay

Özellik | Açıklama
--- | ---
Komut satırı | Derleme öncesi olay aracının uzak sistemde çalıştırılması bir komut satırı belirtir.
Açıklama | Derleme öncesi olay aracının görüntülemesi bir açıklama belirtir.
Derlemede kullan | Bu derleme olayının geçerli yapılandırmada derlemenin dışında tutulup tutulmayacağını belirtir.
Kopyalanacak ek dosyaları | Uzak sistemden kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak liste olarak şunun gibi bir söz dizimi kullanılarak yerel eşleme çiftlerine için sağlanabilir: fullremotepath1: = fulllocalpath1; fulllocalpath2: = fulllocalpath2, burada bir uzak dosya kopyalanabilir yerel makinede belirtilen konuma.

### <a name="remote-post-build-event"></a>Uzaktan derleme sonrası olay

Özellik | Açıklama
--- | ---
Komut satırı | Derleme sonrası olay aracının uzak sistemde çalıştırılması için bir komut satırı belirtir.
Açıklama | Derleme sonrası olay aracının görüntülemesi bir açıklama belirtir.
Derlemede kullan | Bu derleme olayının geçerli yapılandırmada derlemenin dışında tutulup tutulmayacağını belirtir.
Kopyalanacak ek dosyaları | Uzak sistemden kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak liste olarak şunun gibi bir söz dizimi kullanılarak yerel eşleme çiftlerine için sağlanabilir: fullremotepath1: = fulllocalpath1; fulllocalpath2: = fulllocalpath2, burada bir uzak dosya kopyalanabilir yerel makinede belirtilen konuma.

## <a name="cc"></a>C/C++

### <a name="intellisense"></a>IntelliSense

IntelliSense özelliklerini ipuçları IntelliSense altyapısı sağlamak için proje veya dosya düzeyinde ayarlanabilir. Derleme etkilemez.

Özellik | Açıklama
--- | ---
Arama Yolu Ekle | Eklenen dosyaların çözümlenmesi için ekleme kodu arama yolunu belirtir.
Zorlanmış içerir | Dahil edilen zorlanarak eklenmiş dosyaları belirtir.
Önişlemci tanımları | Kullanılan kaynak kodları tarafından önişlemci tanımlarını belirtir.
Ön İşlemci tanımlarını Kaldır | Bir veya daha çok önişlemci tanımsızı belirtir.     (/U[makro]))
Ek Seçenekler | C++ dosyaları ayrıştırılırken IntelliSense tarafından kullanılacak ek derleyici anahtarlarını belirtir.

### <a name="build"></a>Yapı

Özellik | Açıklama
--- | ---
Komut satırı derleme | 'Build' komutu için çalıştırılacak komut satırını belirtir.
Rebuild all komut satırı | 'Tümünü yeniden derle' komutu için çalıştırılacak komut satırını belirtir.
Temizle komut satırı | 'Temizle' komutu için çalıştırılacak komut satırını belirtir.

### <a name="remote-build"></a>Uzak derleme

Özellik | Açıklama
--- | ---
Komut satırı derleme | 'Build' komutu için çalıştırılacak komut satırını belirtir. Bu, uzak sistemde çalıştırılır.
Rebuild all komut satırı | 'Tümünü yeniden derle' komutu için çalıştırılacak komut satırını belirtir. Bu, uzak sistemde çalıştırılır.
Temizle komut satırı | 'Temizle' komutu için çalıştırılacak komut satırını belirtir. Bu, uzak sistemde çalıştırılır.
Çıktılar | Uzak sistemdeki Uzak derleme tarafından oluşturulan çıkışları belirtir.

::: moniker-end
