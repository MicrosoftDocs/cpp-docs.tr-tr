---
title: Genel Özellikler (Linux C++ Makefile Project)| Microsoft Dokümanlar
ms.date: 06/07/2019
ms.assetid: 3dec6853-43f6-412b-9806-9bfad333a204
ms.openlocfilehash: 72a7919bc94be80acdbf7a2cef5b4a9875595545
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "79446158"
---
# <a name="makefile-project-properties-linux-c"></a>Makefile Proje Özellikleri (Linux C++)

::: moniker range="vs-2015"

Linux desteği Visual Studio 2017 ve sonrası sürümlerinde kullanılabilir.

::: moniker-end

::: moniker range=">=vs-2017"

Bu, Bir Linux Makefile projesinde bulunan özelliklerin kısmi bir listesidir. Birçok Makefile proje özelliği Linux C++ Console Application proje özellikleriyle aynıdır.

## <a name="general"></a>Genel

| Özellik | Açıklama | Seçenekler |
|--|--|--|
| Çıktı Dizini | Çıktı dosyası dizinine göreli bir yol belirtir; çevre değişkenlerini içerebilir. |
| Orta Dizini | Ara dosya dizinine göreli bir yol belirtir; çevre değişkenlerini içerebilir. |
| Günlük Dosyası Oluştur | Yapı günlüğü etkinleştirildiğinde yazılması gereken yapı günlüğü dosyasını belirtir. |
| Yapılandırma Türü | Bu yapılandırmanın oluşturduğu çıktı türünü belirtir. | **Dinamik Kitaplık (.so)** - Dinamik Kitaplık (.so)<br>**Statik kitaplık (.a)** - Statik Kitaplık (.a)<br>**Uygulama (.out)** - Uygulama (.out)<br>**Makefile** - Makefile<br> |
| Uzaktan Yapı Makinesi | Uzaktan oluşturma, dağıtma ve hata ayıklama için kullanılacak hedef makine veya aygıt. |
| Uzaktan Yapı Kök Dizini | Uzak makine veya aygıttaki bir dizin için bir yol belirtir. |
| Uzaktan Yapı Proje Dizini | Proje için uzak makine veya aygıtta bir dizin için bir yol belirtir. |

## <a name="debugging"></a>Hata Ayıklama

Bkz. [Hata Ayıklama Özellikleri (Linux C++)](debugging-linux.md)

## <a name="copy-sources"></a>Kaynakları Kopyala

Bkz. [Kopyalama Kaynakları Proje Özellikleri (Linux C++)](copy-sources-project.md).

## <a name="build-events"></a>Etkinlikler Oluşturun

### <a name="pre-build-event"></a>Ön Yapı Etkinliği

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Önceden yapı olay aracının çalışması için bir komut satırı belirtir. |
| Açıklama | Önceden yapı olay aracının görüntülenmesi için bir açıklama belirtir. |
| Yapı'da Kullanım | Bu yapı olayının geçerli yapılandırma için yapının dışında kalıp kalmayacağını belirtir. |
| Kopyalanması gereken ek dosyalar | Uzak sisteme kopyalanması için ek dosyalar belirtir. İsteğe bağlı olarak liste, bunun gibi bir sözdizimini kullanarak uzaktan eşleme çiftleri için yerel olarak sağlanabilir: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2, yerel bir dosya uzak sistemde belirtilen uzak konuma kopyalanabilir. |

### <a name="post-build-event"></a>Yapı Sonrası Etkinlik

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Yapı sonrası olay aracının çalışması için bir komut satırı belirtir. |
| Açıklama | Yapı sonrası olay aracının görüntülenmesi için bir açıklama belirtir. |
| Yapı'da Kullanım | Bu yapı olayının geçerli yapılandırma için yapının dışında kalıp kalmayacağını belirtir. |
| Kopyalanması gereken ek dosyalar | Uzak sisteme kopyalanması için ek dosyalar belirtir. İsteğe bağlı olarak liste, bunun gibi bir sözdizimini kullanarak uzaktan eşleme çiftleri için yerel olarak sağlanabilir: fulllocalpath1:=fullremotepath1;fulllocalpath2:=fullremotepath2, yerel bir dosya uzak sistemde belirtilen uzak konuma kopyalanabilir. |

### <a name="remote-pre-build-event"></a>Uzaktan Ön Yapı Etkinliği

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Önceden inşa edilen olay aracının uzak sistemde çalışması için bir komut satırı belirtir. |
| Açıklama | Önceden yapı olay aracının görüntülenmesi için bir açıklama belirtir. |
| Yapı'da Kullanım | Bu yapı olayının geçerli yapılandırma için yapının dışında kalıp kalmayacağını belirtir. |
| Kopyalanması gereken ek dosyalar | Uzak sistemden kopyalanması gereken ek dosyaları belirtir. İsteğe bağlı olarak liste, aşağıdaki gibi bir sözdizimi kullanarak yerel eşleme çiftleri için uzaktan kullanılabilir: fullremotepath1:=fulllocalpath1;fullremotepath2:=fulllocalpath2, uzak bir dosyayerel makinede belirtilen konuma kopyalanabilir. |

### <a name="remote-post-build-event"></a>Uzaktan Post-Build Etkinliği

| Özellik | Açıklama |
|--|--|
| Komut Satırı | Yapı sonrası olay aracının uzak sistemde çalışması için bir komut satırı belirtir. |
| Açıklama | Yapı sonrası olay aracının görüntülenmesi için bir açıklama belirtir. |
| Yapı'da Kullanım | Bu yapı olayının geçerli yapılandırma için yapının dışında kalıp kalmayacağını belirtir. |
| Kopyalanması gereken ek dosyalar | Uzak sistemden kopyalanması gereken ek dosyaları belirtir. İsteğe bağlı olarak liste, aşağıdaki gibi bir sözdizimi kullanarak yerel eşleme çiftleri için uzaktan kullanılabilir: fullremotepath1:=fulllocalpath1;fullremotepath2:=fulllocalpath2, uzak bir dosyayerel makinede belirtilen konuma kopyalanabilir. |

## <a name="cc"></a>C/C++

### <a name="intellisense"></a>IntelliSense

IntelliSense özellikleri, IntelliSense motoruna ipucu sağlamak için proje veya dosya düzeyinde ayarlanabilir. Derlemeyi etkilemez.

| Özellik | Açıklama |
|--|--|
| Arama Yolu Ekle | Dahil edilen dosyaları çözmek için dahil arama yolunu belirtir. |
| Zorla Içerir | Zorla dahil edilen dosyaları belirtir. |
| Önişlemci Tanımları | Kaynak dosyalar tarafından kullanılan önişlemci tanımlarını belirtir. |
| Tanımsız Önİşlemci Tanımları | Bir veya daha fazla önişlemci tanımlanmamış belirtir.     (/U[makro]) |
| Ek Seçenekler | C++ dosyalarını ayrıştirırken IntelliSense tarafından kullanılacak ek derleyici anahtarlarını belirtir. |

### <a name="build"></a>Yapı

| Özellik | Açıklama |
|--|--|
| Komut Satırı Oluştur | 'Yapı' komutu için çalışacak komut satırını belirtir. |
| Tüm Komut Satırlarını Yeniden Oluştur | 'Tümlerini Yeniden Oluştur' komutu için çalışacak komut satırını belirtir. |
| Komut SatırLarını Temizle | 'Temiz' komutu için çalışacak komut satırını belirtir. |

### <a name="remote-build"></a>Uzaktan Yapı

| Özellik | Açıklama |
|--|--|
| Komut Satırı Oluştur | 'Yapı' komutu için çalışacak komut satırını belirtir. Bu uzak sistemde yürütülür. |
| Tüm Komut Satırlarını Yeniden Oluştur | 'Tümlerini Yeniden Oluştur' komutu için çalışacak komut satırını belirtir. Bu uzak sistemde yürütülür. |
| Komut SatırLarını Temizle | 'Temiz' komutu için çalışacak komut satırını belirtir. Bu uzak sistemde yürütülür. |
| Çıkışlar | Uzak sistem üzerinde uzaktan yapı tarafından oluşturulan çıkışları belirtir. |

::: moniker-end
