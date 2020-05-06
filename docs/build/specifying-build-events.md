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
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62315241"
---
# <a name="specifying-build-events"></a>Derleme olaylarını belirtme

Derleme başlamadan önce, bağlantı işleminden önce veya oluşturma bittikten sonra çalışan komutları belirtmek için derleme olaylarını kullanabilirsiniz.

Derleme olayları yalnızca derleme yapı sürecinde bu noktalara başarıyla ulaşırsa yürütülür. Derlemede bir hata oluşursa, *Derleme sonrası* olay oluşmaz; hata, bağlama aşamasından önce oluşursa, *ön bağlantı* veya *Derleme sonrası* olay oluşur. Ayrıca, herhangi bir dosyanın bağlanması gerekmiyorsa, *bağlama öncesi* olay gerçekleşmez. Bağlama *öncesi* olay, bağlantı adımı içermeyen projelerde de kullanılamaz.

Oluşturulacak dosyanın oluşturulması gerekmiyorsa, hiçbir derleme olayı gerçekleşmez.

Derleme olayları hakkında genel bilgi için bkz. [özel yapı adımlarını anlama ve olayları oluşturma](understanding-custom-build-steps-and-build-events.md).

### <a name="to-specify-a-build-event"></a>Derleme olayı belirtmek için

1. **Çözüm Gezgini**, yapı olayını belirtmek istediğiniz projeyi seçin.

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Daha fazla bilgi için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](working-with-project-properties.md).

1. **Derleme olayları** klasöründe, bir derleme olayı Özellik sayfası seçin.

1. Derleme olayı ile ilişkili özellikleri belirtin:

   - Komut **satırında**, komut isteminde şunu belirtmiş gibi bir komut belirtin. Geçerli bir komut veya toplu iş dosyası ve gerekli giriş veya çıkış dosyalarını belirtin. Sonraki tüm komutların yürütüldüğünü garantilemek için bir toplu iş dosyasının adından önce Batch komutunu **çağır** komutunu belirtin.

      Birden çok giriş ve çıkış dosyası, MSBuild makroları ile sembosel olarak belirtilebilir. Dosyaların konumunu veya dosya kümelerinin adlarını belirtme hakkında bilgi için bkz. [derleme komutları ve özellikleri Için ortak makrolar](reference/common-macros-for-build-commands-and-properties.md).

      '% ' Karakteri MSBuild tarafından ayrıldığından, bir ortam değişkeni belirtirseniz her **%** kaçış karakterini **%25** onaltılık kaçış dizisi ile değiştirin. Örneğin, **% windir%** öğesini **% 25windir %25**ile değiştirin. MSBuild, ortam değişkenine erişmeden önce her **%25** sırayı **%** karakteriyle değiştirir.

   - **Açıklama**' da bu olay için bir açıklama yazın. Bu olay gerçekleştiğinde Açıklama **Çıkış** penceresine yazdırılır.

   - **Derlemeden hariç tutulmazsa**, olayın çalıştırılmasını istemiyorsanız **Evet** ' i belirtin.

## <a name="see-also"></a>Ayrıca bkz.

[Özel Derleme Adımlarını ve Derleme Olaylarını Anlama](understanding-custom-build-steps-and-build-events.md)<br>
[Derleme komutları ve özellikleri için ortak makrolar](reference/common-macros-for-build-commands-and-properties.md)<br>
[Derleme Özelleştirmeleri Sorunlarını Giderme](troubleshooting-build-customizations.md)
