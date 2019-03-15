---
title: Derleme Olayları Belirtme
ms.date: 12/28/2017
f1_keywords:
- VC.Project.IVCEventTool.CommandLine
- VC.Project.IVCEventTool.ExcludedFromBuild
- VC.Project.IVCEventTool.Description
helpviewer_keywords:
- Pre-Link event
- build events [C++], specifying
- custom build steps [C++], build events
- builds [C++], events
- events [C++], build
- builds [C++], customizing C++
- build events [C++]
- post-build events
ms.assetid: 788a6c18-2dbe-4a49-8cd6-86c1ad7a95cc
ms.openlocfilehash: c8097e013f934c45b8e3860b8377bdb2bdb9d9a0
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57823982"
---
# <a name="specifying-build-events"></a>Derleme olayları belirtme

Derleme olayları oluşturma, bağlama işlemini önce başlamadan önce veya derleme tamamlandıktan sonra çalışan komutlar belirtmek için kullanabilirsiniz.

Derleme olayları, yalnızca derlemenin yapı işleminde bu noktaları başarıyla ulaşırsa yürütülür. Yapı, bir hata oluşursa *derleme sonrası* olay gerçekleştirilmez; hata bağlama aşamasından önce tipleri oluşursa *bağlama öncesi* ya da *derleme sonrası* olay gerçekleşir. Ayrıca, bağlanması gereken dosya yok *bağlama öncesi* olay oluşmaz. *Bağlama öncesi* olay değil de bir bağlantı adım içermeyen projelerinde kullanılabilir.

Hiçbir dosya oluşturulacak gerekiyorsa, hiçbir derleme olayları oluşur.

Derleme olayları hakkında genel bilgi için bkz. [anlama özel derleme adımlarını ve derleme olaylarını](understanding-custom-build-steps-and-build-events.md).

### <a name="to-specify-a-build-event"></a>Derleme olayı belirtmek için

1. İçinde **Çözüm Gezgini**, derleme olayı belirtmek istediğiniz projeyi seçin.

1. Projenin açın **özellik sayfaları** iletişim kutusu. Daha fazla bilgi için [Visual Studio'da ayarlayın C++ derleyicisi ve derleme özellikleri](working-with-project-properties.md).

1. İçinde **Build Events** klasöründe bir derleme olay özellik sayfasını seçin.

1. Derleme olayla ilişkili özellikleri belirtin:

   - İçinde **komut satırı**, komut isteminde belirtme gibi bir komutu belirtin. Geçerli komut veya toplu iş dosyasını belirtin ve tüm gerekli giriş veya çıkış dosyalarını. Belirtin **çağrı** toplu tüm komutlar yürütülür garanti etmek için önce bir toplu iş dosyası adını komutu.

      Birden çok giriş ve çıkış dosyalarının bildirmelerine MSBuild makroları ile belirtilebilir. Dosyalarının konumu veya dosya kümelerini adlarını belirtme hakkında daha fazla bilgi için bkz: [derleme komutları ve özellikler için ortak makroları](reference/common-macros-for-build-commands-and-properties.md).

      Her bir ortam değişkenini Değiştir belirtirseniz, '%' karakter MSBuild tarafından ayrılmış olduğundan **%** kaçış karakteriyle **% 25** onaltılı çıkış dizisi. Örneğin, **% WINDIR %** ile **25WINDIR % 25**. MSBuild değiştirir her **% 25** ile sıralı **%** ortam değişkenini erişmeden önce karakter.

   - İçinde **açıklama**, bu olay için bir açıklama yazın. Açıklama yazdırıldığında **çıkış** bu olay meydana geldiğinde penceresi.

   - İçinde **yapıdan hariç**, belirtin **Evet** çalıştırmak için olay istemiyorsanız.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Derleme Adımlarını ve Derleme Olaylarını Anlama](understanding-custom-build-steps-and-build-events.md)<br>
[Genel derleme komutları ve Özellikler makroları](reference/common-macros-for-build-commands-and-properties.md)<br>
[Derleme Özelleştirmeleri Sorunlarını Giderme](troubleshooting-build-customizations.md)
