---
title: /INCREMENTAL (Artımlı Bağla)
ms.date: 11/04/2016
f1_keywords:
- /incremental
- VC.Project.VCLinkerTool.LinkIncremental
helpviewer_keywords:
- /INCREMENTAL linker option
- -INCREMENTAL linker option
- INCREMENTAL linker option
- link incrementally option
- LINK tool [C++], options for full linking
- incremental linking
ms.assetid: 135656ff-94fa-4ad4-a613-22e1a2a5d16b
ms.openlocfilehash: 0ef6e8c7fed2c58e8fc2949a84483015bbc9d6bc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50642035"
---
# <a name="incremental-link-incrementally"></a>/INCREMENTAL (Artımlı Bağla)

```
/INCREMENTAL[:NO]
```

## <a name="remarks"></a>Açıklamalar

Bağlayıcının artımlı bağlamayı nasıl işlediğini denetler.

Varsayılan olarak bağlayıcı artımlı modda çalışır. Varsayılan bir artırımlı bağlantıyı geçersiz kılmak için /INCREMENTAL:NO belirtin.

Artımlı bağlanan program, artımlı olmayan bağlanan programa işlevsel olarak eşdeğerdir. Ancak, sonraki artımlı bağlantılar, bir artımlı olarak bağlı yürütülebilir, statik kitaplık veya dinamik bağlantı kitaplığı dosyası için hazırlandığından:

- Kod ve veri doldurma nedeniyle, artımlı olmayan bağlanan bir programdan büyüktür. Doldurma, bağlayıcının dosyayı yeniden oluşturmanıza gerek kalmadan işlevler ve veriler boyutunu artırmak sağlar.

- İşlevlerin yeni adreslerine tanıtılması için atlama dönüştürücüler içerebilir.

   > [!NOTE]
   > Son yayın derlemenizin doldurma veya dönüştürücü içermemesini içermediğinden emin olmak için programınızı artımlı olmayan Bağla.

Varsayılandan bağımsız ve artırımlı olarak bağlamak için /INCREMENTAL belirtin. Bu seçenek belirlendiğinde, bağlayıcı artımlı olarak bağlanamadığında bir uyarı verir ve sonra da programı artımlı olmayan bağlar. Belirli seçenekler ve durumlar /INCREMENTAL öğesini geçersiz kılar.

Çoğu program kademeli olarak bağlanabilir. Ancak bası değişiklikler çok büyük değildir ve bazı seçenekler artımlı bağlama ile uyumlu değildir. LINK, aşağıdaki seçeneklerden herhangi biri belirtilirse tam bağlantı gerçekleştirir:

- Artımlı Bağlantı seçili değil (/INCREMENTAL:NO)

- /OPT:REF seçili

- /OPT:ICF seçili

- /OPT:LBR seçili

- /ORDER seçili

/ INCREMENTAL, örtük [/DEBUG](../../build/reference/debug-generate-debug-info.md) belirtilir.

Ayrıca, aşağıdaki durumlardan herhangi biri söz konusu olursa LINK tam bağlantı gerçekleştirir:

- Artımlı durum (.ilk) dosyası eksik. (LINK ileride artımlı bağlamaya hazırlık olarak yeni bir .ilk dosyası oluşturur.)

- .ilk dosyası için hiçbir yazma izni yoktur. (Bağlantı .ilk dosyasını ve bağlantıları artımlı olmayan yok sayar.)

- .exe veya .dll çıktı dosyası eksik.

- .ilk, .exe veya .dll'nin zaman damgası değişmiş.

- LINK seçeneği değiştirilir. Yapılar arasında değiştirildiğinde çoğu bağlantı seçenekleri, tam bir bağlantıya neden olur.

- Bir nesne (.obj) dosyası eklendi veya atlandı.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin açın **özellik sayfaları** iletişim kutusu. Ayrıntılar için bkz [Working with Project Properties](../../ide/working-with-project-properties.md).

1. Seçin **bağlayıcı** klasör.

1. Seçin **genel** özellik sayfası.

1. Değiştirme **artımlı bağlamayı etkinleştir** özelliği.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkIncremental%2A>.

## <a name="see-also"></a>Ayrıca Bkz.

[Bağlayıcı Seçeneklerini Ayarlama](../../build/reference/setting-linker-options.md)<br/>
[Bağlayıcı Seçenekleri](../../build/reference/linker-options.md)