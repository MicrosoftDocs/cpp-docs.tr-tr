---
title: vcpkg komut satırı başvurusu
description: Windows, macOS ve Linux 'ta vcpkg için komut satırı seçeneklerini nasıl kullanacağınızı öğrenin.
ms.date: 12/17/2020
ms.topic: reference
ms.technology: cpp-ide
ms.openlocfilehash: d60ebf983fea2eb41430f05b8c12e4a4a6fe370b
ms.sourcegitcommit: 2b2c3fa9244e31db35ea33554dea0efcab490f3c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/18/2020
ms.locfileid: "97684261"
---
# <a name="vcpkg-command-line-reference"></a>vcpkg komut satırı başvurusu

Vcpkg 'da kullanılabilen komutlara hızlı bir başvuru.

## <a name="commands"></a>Komutlar

| Komut | Açıklama |
|--|--|
| **`vcpkg search [pat]`** | Yüklemek için kullanılabilir paketleri ara |
| **`vcpkg install <pkg>...`** | Paketi yükleme |
| **`vcpkg remove <pkg>...`** | Bir paketi kaldırma |
| **`vcpkg remove --outdated`** | Tüm güncel paketleri kaldır |
| **`vcpkg list`** | Yüklü paketleri Listele |
| **`vcpkg update`** | Güncelleştirme için paketlerin listesini görüntüle |
| **`vcpkg upgrade`** | Tüm eski paketleri yeniden derle |
| **`vcpkg hash <file> [alg]`** | Belirli bir algoritmayla bir dosyayı karma, varsayılan SHA512 olur |
| **`vcpkg integrate install`** | Yüklü paketleri Kullanıcı genelinde kullanılabilir hale getirin. İlk kullanımda yönetici ayrıcalıkları gerektirir |
| **`vcpkg integrate remove`** | Kullanıcı genelinde tümleştirmeyi kaldırma |
| **`vcpkg integrate project`** | Tek tek VS projesi kullanımı için başvuran bir NuGet paketi oluşturma |
| **`vcpkg export <pkg>... [opt]...`** | Paketi dışarı aktarma |
| **`vcpkg edit <pkg>`** | Düzenleme için bir bağlantı noktası açın (% EDITOR%, varsayılan ' Code ' kullanır) |
| **`vcpkg create <pkg> <url> [archivename]`** | Yeni bir paket oluştur |
| **`vcpkg cache`** | Önbelleğe alınmış derlenmiş paketleri Listele |
| **`vcpkg version`** | Sürüm bilgilerini görüntüle |
| **`vcpkg contact --survey`** | Geri bildirim göndermek için kişi bilgilerini görüntüleyin. |

## <a name="options"></a>Seçenekler

| Seçenek | Açıklama |
|--|--|
| **`--triplet <t>`** | Hedef mimari, Üçlü mimari belirtin. (varsayılan: `%VCPKG_DEFAULT_TRIPLET%` , Ayrıca bkz. **`vcpkg help triplet`** ) |
| **`--vcpkg-root <path>`** | Vcpkg kök dizinini belirtin (varsayılan: `%VCPKG_ROOT%` ) |

## <a name="see-also"></a>Ayrıca bkz.

[vcpkg: Windows, Linux ve macOS için C++ Paket Yöneticisi](./vcpkg.md)\
[GitHub üzerinde vcpkg](https://github.com/Microsoft/vcpkg)\
[Vcpkg 'yi yükler](install-vcpkg.md)\
[Vcpkg 'yi tümleştirin](integrate-vcpkg.md)\
[Vcpkg ile kitaplıkları yönetme](manage-libraries-with-vcpkg.md)\
[Hızlı başlangıç](https://github.com/microsoft/vcpkg/blob/master/docs/index.md)\
[Sık sorulan sorular](https://github.com/microsoft/vcpkg/blob/master/docs/about/faq.md)
