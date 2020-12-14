---
description: Daha fazla bilgi edinin:/artımlı (artımlı bağlantı)
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
ms.openlocfilehash: 4b115bd88bed5b012c29c3d0e61d471aa869b78a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191296"
---
# <a name="incremental-link-incrementally"></a>/INCREMENTAL (Artımlı Bağla)

```
/INCREMENTAL[:NO]
```

## <a name="remarks"></a>Açıklamalar

Bağlayıcının artımlı bağlamayı nasıl işlediğini denetler.

Varsayılan olarak bağlayıcı artımlı modda çalışır. Varsayılan bir artırımlı bağlantıyı geçersiz kılmak için /INCREMENTAL:NO belirtin.

Artımlı bağlantılı program, artımlı olmayan bağlantılı bir programa işlevsel olarak eşdeğerdir. Ancak, sonraki artımlı bağlantılar için hazırlandığından, artımlı olarak bağlanmış bir çalıştırılabilir, statik kitaplık veya dinamik bağlantı kitaplığı dosyası:

- , Kod ve veri doldurma nedeniyle artımlı olmayan bağlantılı bir programdan daha büyük. Doldurma, bağlayıcının, dosyayı yeniden oluşturmadan işlevlerin ve verilerin boyutunu artırmalarını sağlar.

- İşlevlerin yeni adreslerine tanıtılması için atlama dönüştürücüler içerebilir.

   > [!NOTE]
   > Son Yayın yapınızı doldurma veya dönüştürücüler içermediğinden emin olmak için programınızı artımlı olmayan şekilde bağlayın.

Varsayılandan bağımsız ve artırımlı olarak bağlamak için /INCREMENTAL belirtin. Bu seçenek belirlendiğinde, bağlayıcı artımlı olarak bağlanamadığında bir uyarı verir ve sonra da programı artımlı olmayan şekilde bağlar. Belirli seçenekler ve durumlar /INCREMENTAL öğesini geçersiz kılar.

Çoğu program kademeli olarak bağlanabilir. Ancak bası değişiklikler çok büyük değildir ve bazı seçenekler artımlı bağlama ile uyumlu değildir. LINK, aşağıdaki seçeneklerden herhangi biri belirtilirse tam bağlantı gerçekleştirir:

- Artımlı Bağlantı seçili değil (/INCREMENTAL:NO)

- /OPT:REF seçili

- /OPT:ICF seçili

- /OPT:LBR seçili

- /ORDER seçili

[/INCRE/Debug](debug-generate-debug-info.md) belirtildiğinde uygulanır.

Ayrıca, aşağıdaki durumlardan herhangi biri söz konusu olursa LINK tam bağlantı gerçekleştirir:

- Artımlı durum (.ilk) dosyası eksik. (LINK ileride artımlı bağlamaya hazırlık olarak yeni bir .ilk dosyası oluşturur.)

- .ilk dosyası için hiçbir yazma izni yoktur. (Bağlantı. ilk dosyasını yoksayar ve artımlı olmayan bağlantıları yok sayar.)

- .exe veya .dll çıktı dosyası eksik.

- .ilk, .exe veya .dll'nin zaman damgası değişmiş.

- LINK seçeneği değiştirilir. Yapılar arasında değiştirildiğinde çoğu bağlantı seçenekleri, tam bir bağlantıya neden olur.

- Bir nesne (.obj) dosyası eklendi veya atlandı.

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Visual Studio geliştirme ortamındaki bu bağlayıcı seçeneğini ayarlamak için

1. Projenin **Özellik sayfaları** iletişim kutusunu açın. Ayrıntılar için bkz. [Visual Studio 'Da C++ derleyicisini ve derleme özelliklerini ayarlama](../working-with-project-properties.md).

1. **Bağlayıcı** klasörünü seçin.

1. **Genel** özellik sayfasını seçin.

1. **Artımlı bağlamayı etkinleştir** özelliğini değiştirin.

### <a name="to-set-this-linker-option-programmatically"></a>Bu bağlayıcı seçeneğini program aracılığıyla ayarlamak için

1. Bkz. <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.LinkIncremental%2A>.

## <a name="see-also"></a>Ayrıca bkz.

[MSVC bağlayıcı başvurusu](linking.md)<br/>
[MSVC bağlayıcı seçenekleri](linker-options.md)
