---
title: Genel Özellikler (Linux C++ makefile Projesi) | Microsoft Docs
ms.date: 06/07/2019
ms.assetid: 3dec6853-43f6-412b-9806-9bfad333a204
ms.openlocfilehash: 72a7919bc94be80acdbf7a2cef5b4a9875595545
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446158"
---
# <a name="makefile-project-properties-linux-c"></a>Makefile proje özellikleri (Linux C++)

::: moniker range="vs-2015"

Linux desteği, Visual Studio 2017 ve üzeri sürümlerde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

Bu, bir Linux makefile projesinde bulunan özelliklerin kısmi bir listesidir. Birçok makefile proje özelliği, Linux C++ konsol uygulaması proje özellikleriyle aynıdır.

## <a name="general"></a>Genel

| Özellik | Açıklama | Yapabileceği |
|--|--|--|
| Çıkış dizini | Çıkış dosyası dizinine göreli bir yol belirtir; ortam değişkenlerini içerebilir. |
| Ara Dizin | Ara dosya dizinine göreli bir yol belirtir; ortam değişkenlerini içerebilir. |
| Derleme günlüğü dosyası | Derleme günlüğü etkinken yazılacak olan derleme günlüğü dosyasını belirtir. |
| Yapılandırma türü | Bu yapılandırmanın oluşturduğu çıkışın türünü belirtir. | **Dinamik kitaplık (. so)** -dinamik kitaplık (. so)<br>**Statik kitaplık (. a)** -statik kitaplık (. a)<br>**Uygulama (. out)** -uygulama (. out)<br>**Makefile** -makefile<br> |
| Uzak derleme makinesi | Uzaktan derleme, dağıtma ve hata ayıklama için kullanılacak hedef makine veya cihaz. |
| Uzak derleme kök dizini | Uzak makine veya cihazdaki bir dizinin yolunu belirtir. |
| Uzak derleme proje dizini | Proje için uzak makine veya cihazdaki bir dizinin yolunu belirtir. |

## <a name="debugging"></a>Hata ayıklama

Bkz. [hata ayıklayıcı özellikleri C++(Linux)](debugging-linux.md)

## <a name="copy-sources"></a>Kaynakları Kopyala

Bkz. [kaynakları kopyalama Projesi Özellikleri ( C++Linux)](copy-sources-project.md).

## <a name="build-events"></a>Derleme olayları

### <a name="pre-build-event"></a>Oluşturma öncesi olay

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Oluşturma öncesi olay aracının çalışması için bir komut satırı belirtir. |
| Açıklama | Oluşturma öncesi olay aracının görüntülemesi için bir açıklama belirtir. |
| Derlemede kullan | Bu derleme olayının, geçerli yapılandırma için derlemeden dışlanıp dışlanmadığını belirtir. |
| Kopyalanacak ek dosyalar | Uzak sisteme kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak, liste, yerel bir dosyanın uzak sistemdeki belirtilen uzak konuma kopyalanabilen şu şekilde bir sözdizimi kullanılarak uzak eşleme çiftleri olarak belirlenebilir: fulllocalpath1: = fullremotepath1; fulllocalpath2: = fullremotepath2. |

### <a name="post-build-event"></a>Oluşturma sonrası olay

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Oluşturma sonrası olay aracının çalışması için bir komut satırı belirtir. |
| Açıklama | Oluşturma sonrası olay aracının görüntülemesi için bir açıklama belirtir. |
| Derlemede kullan | Bu derleme olayının, geçerli yapılandırma için derlemeden dışlanıp dışlanmadığını belirtir. |
| Kopyalanacak ek dosyalar | Uzak sisteme kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak, liste, yerel bir dosyanın uzak sistemdeki belirtilen uzak konuma kopyalanabilen şu şekilde bir sözdizimi kullanılarak uzak eşleme çiftleri olarak belirlenebilir: fulllocalpath1: = fullremotepath1; fulllocalpath2: = fullremotepath2. |

### <a name="remote-pre-build-event"></a>Uzaktan derleme öncesi olay

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Oluşturma öncesi olay aracının uzak sistemde çalıştırılması için bir komut satırı belirtir. |
| Açıklama | Oluşturma öncesi olay aracının görüntülemesi için bir açıklama belirtir. |
| Derlemede kullan | Bu derleme olayının, geçerli yapılandırma için derlemeden dışlanıp dışlanmadığını belirtir. |
| Kopyalanacak ek dosyalar | Uzak sistemden kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak, liste, yerel makinede belirtilen konuma bir uzak dosya kopyalanabilen şu şekilde bir söz dizimi kullanılarak yerel eşleme çiftleri olarak belirlenebilir: fullremotepath1: = fulllocalpath1; fullremotepath2: = fulllocalpath2. |

### <a name="remote-post-build-event"></a>Oluşturma sonrası uzak olay

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Oluşturma sonrası olay aracının uzak sistemde çalıştırılması için bir komut satırı belirtir. |
| Açıklama | Oluşturma sonrası olay aracının görüntülemesi için bir açıklama belirtir. |
| Derlemede kullan | Bu derleme olayının, geçerli yapılandırma için derlemeden dışlanıp dışlanmadığını belirtir. |
| Kopyalanacak ek dosyalar | Uzak sistemden kopyalanacak ek dosyaları belirtir. İsteğe bağlı olarak, liste, yerel makinede belirtilen konuma bir uzak dosya kopyalanabilen şu şekilde bir söz dizimi kullanılarak yerel eşleme çiftleri olarak belirlenebilir: fullremotepath1: = fulllocalpath1; fullremotepath2: = fulllocalpath2. |

## <a name="cc"></a>C/C++

### <a name="intellisense"></a>IntelliSense

IntelliSense 'in özellikleri, IntelliSense altyapısına ipuçları sağlamak için proje veya dosya düzeyinde ayarlanabilir. Derlemeyi etkilemez.

| Özellik | Açıklama |
|--|--|
| Arama yolunu ekle | Dahil edilen dosyaları çözümlemek için ekleme arama yolunu belirtir. |
| Zorunlu ekler | Zorla eklenen dosyaları belirtir. |
| Önişlemci tanımları | Kaynak dosyalar tarafından kullanılan Önişlemci tanımlarını belirtir. |
| Önişlemci tanımlarının tanımı kaldırılıyor | Bir veya daha fazla önişlemci tarafından tanımlanabileceğini belirtir.     (/U [makro]) |
| Ek Seçenekler | Dosya ayrıştırılırken C++ IntelliSense tarafından kullanılacak ek derleyici anahtarlarını belirtir. |

### <a name="build"></a>Oluşturma

| Özellik | Açıklama |
|--|--|
| Derleme komut satırı | ' Build ' komutu için çalıştırılacak komut satırını belirtir. |
| Tüm komut satırını yeniden derle | ' Tümünü yeniden derle ' komutu için çalıştırılacak komut satırını belirtir. |
| Temizle komut satırı | ' Temizle ' komutu için çalıştırılacak komut satırını belirtir. |

### <a name="remote-build"></a>Uzak derleme

| Özellik | Açıklama |
|--|--|
| Derleme komut satırı | ' Build ' komutu için çalıştırılacak komut satırını belirtir. Bu, uzak sistemde yürütülür. |
| Tüm komut satırını yeniden derle | ' Tümünü yeniden derle ' komutu için çalıştırılacak komut satırını belirtir. Bu, uzak sistemde yürütülür. |
| Temizle komut satırı | ' Temizle ' komutu için çalıştırılacak komut satırını belirtir. Bu, uzak sistemde yürütülür. |
| Çıkışlar | Uzak sistemdeki uzak derleme tarafından oluşturulan çıkışları belirtir. |

::: moniker-end
