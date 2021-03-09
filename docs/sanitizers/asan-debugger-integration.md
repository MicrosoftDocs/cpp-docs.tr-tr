---
title: Visual Studio Addresstemizleme genişletilmiş işlevsellik kitaplığı (VCASan)
description: Vcasan. lib teknik açıklaması.
ms.date: 03/02/2021
f1_keywords:
- vcasan
helpviewer_keywords:
- vcasan.lib
- vcasan
- vcasand.lib
- libvcasan.lib
- libvcasand.lib
ms.openlocfilehash: 8728fead94b5d2b4827b34f1a5461c08c821f2e7
ms.sourcegitcommit: 6ed44d9c3fb32e965e363b9c69686739a90a2117
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/08/2021
ms.locfileid: "102470722"
---
# <a name="visual-studio-addresssanitizer-extended-functionality-library-vcasan"></a>Visual Studio Addresstemizleme genişletilmiş işlevsellik kitaplığı (VCAsan)

*`VCAsan*.lib`* Kitaplıklar, Visual Studio 'da genişletilmiş hata AYıKLAYıCı IDE özellikleri uygular. Bu özellikler, IDE 'nin canlı hata ayıklama oturumlarında Adrestemizleme hatalarını göstermesini sağlar veya bir kilitlenme bilgi döküm dosyasını meta verilerle kaydederek çevrimdışı hale getirir. Bu kitaplık, Addresstemizleyerek MSVC derleyicisi tarafından etkin olduğu zaman bağlanır.

## <a name="vcasan-library-inventory"></a>VCAsan kitaplığı envanteri

| Çalışma zamanı seçeneği | VCAsan bağlantı kitaplığı  |
|---------------|----------------------|
| **`/MT`**           | *`libvcasan.lib`*        |
| **`/MD`**           | *`vcasan.lib`*           |
| **`/MTd`**          | *`libvcasand.lib`*       |
| **`/MDd`**          | *`vcasand.lib`*          |

## <a name="vcasan-library-features"></a>VCAsan kitaplığı özellikleri

### <a name="rich-addresssanitizer-error-report-window-in-visual-studio-ide"></a>Visual Studio IDE 'de zengin Addresstemizleme hatası rapor penceresi

VCAsan kitaplığı, arabirim işlevini kullanarak Addresstemizleme çalışma zamanı içinde bir geri çağırma kaydeder [`__asan_set_error_report_callback`](https://github.com/llvm/llvm-project/blob/1ba5ea67a30170053964a28f2f47aea4bb7f5ff1/compiler-rt/include/sanitizer/asan_interface.h#L256) . Bir Addresstemizleyerek rapor oluşturulursa, bu geri çağırma, Visual Studio tarafından yakalanan bir özel durum oluşturmak için kullanılır. Visual Studio, IDE 'de kullanıcıya görüntülenen iletiyi oluşturmak için özel durum verilerini kullanır.

> [!NOTE]
> VCAsan kitaplığı, Addresstemizleme çalışma zamanına bir geri çağırma işlevi kaydeder. Kodunuz ikinci kez bu kayıt işlevini çağırırsa, VCAsan kitaplığı geri çağırma kaydının üzerine yazar. Bu, tüm Visual Studio IDE tümleştirmesinin kaybedilmesine neden olur. Varsayılan IDE Kullanıcı deneyimine geri döndürürüreceğiz. Ayrıca, bir kullanıcının geri arama işlemini kayıp olarak kaydeden bir çağrı için de mümkündür. Herhangi bir sorunla karşılaşırsanız, bir [hata bildirin](https://aka.ms/feedback/report?space=62).

### <a name="save-addresssanitizer-errors-in-a-new-type-of-crash-dump-file"></a>Yeni kilitlenme bilgi döküm dosyası türünde Addresstemizleme hatalarını Kaydet

VCAsan kitaplığını çalıştırılabilire bağladığınızda, kullanıcılar çalışma zamanında kilitlenme dökümü oluşturmak için bunu etkinleştirebilir. Daha sonra, bir hata oluştuğunda Addresstemizleşme çalışma zamanı bir döküm dosyası oluşturur. Bu özelliği etkinleştirmek için Kullanıcı, `ASAN_SAVE_DUMPS` ortam değişkenini bunun gibi bir komut kullanarak ayarlar:

`set ASAN_SAVE_DUMPS=MyFileName.dmp`

Visual Studio IDE kurallarını izlemek için dosyanın bir. dmp sonekine sahip olması gerekir.

İçin bir döküm dosyası belirtildiğinde bu durum şudur `ASAN_SAVE_DUMPS` : Addresstemizleme çalışma zamanı tarafından bir hata oluşursa, hatayla ilişkili meta verileri içeren bir kilitlenme bilgi döküm dosyası kaydeder. Visual Studio sürüm 16,9 ve sonraki sürümlerde hata ayıklayıcı, döküm dosyasına kaydedilen meta verileri ayrıştırabilirler. `ASAN_SAVE_DUMPS`Test başına temelinde ayarlanabilir, bu ikili yapıtları saklayabilir ve ardından bunları uygun kaynak dizinlemesi Ile IDE 'de görüntüleyebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[Addresstemizme genel bakış](./asan.md)\
[Adrestemizleme bilinen sorunlar](./asan-known-issues.md)\
[Addresstemizleyebilir derleme ve dil başvurusu](./asan-building.md)\
[Addresstemizleme çalışma zamanı başvurusu](./asan-runtime.md)\
[Addresstemizleme gölge baytları](./asan-shadow-bytes.md)\
[Addresstemizleme bulutu veya dağıtılmış test](./asan-offline-crash-dumps.md)\
[Addresstemizleme hatası örnekleri](./asan-error-examples.md)
