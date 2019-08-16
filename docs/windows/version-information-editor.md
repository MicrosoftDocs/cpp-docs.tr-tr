---
title: Sürüm bilgileri Düzenleyicisi (C++)
ms.date: 02/14/2019
f1_keywords:
- vc.editors.version.F1
- vc.editors.version
helpviewer_keywords:
- Version Information editor [C++], about Version Information editor
- editors, Version Information
- resource editors [C++], Version Information editor
- version information resources [C++]
- resources [C++], editing version information
- languages, version information
- New Version Info Block
- blocks, adding
- resources [C++], adding version information
- version information, adding for languages
- blocks, deleting
- version information, deleting blocks
- resources [C++], deleting version information
- VerQueryValue
- version information, accessing from within programs
- GetFileVersionInfo
- version information
ms.assetid: 772e6f19-f765-4cec-9521-0ad3eeb99f9b
ms.openlocfilehash: e68e1480d2cd9a8d8a4d862252e6eb4384a5cd68
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513647"
---
# <a name="version-information-editor-c"></a>Sürüm bilgileri Düzenleyicisi (C++)

Sürüm bilgileri şirket ve ürün kimliği, ürün sürüm numarası ve telif hakkı ve ticari marka bildirimiyle oluşur. **Sürüm bilgileri Düzenleyicisi**ile, sürüm bilgileri kaynağında saklanan bu verileri oluşturur ve korursunuz. Sürüm bilgisi kaynağı bir uygulama için gerekli değildir, ancak uygulamayı tanımlayan bilgileri toplamak yararlı bir yerdir. Sürüm bilgileri, kurulum API 'Leri tarafından da kullanılır.

> [!NOTE]
> Windows Standard 'ın, VS_VERSION_INFO adlı yalnızca bir sürüm kaynağı vardır.

Sürüm bilgileri kaynağında bir üst blok ve bir veya daha fazla alt blok bulunur: en üstteki tek bir sabit bilgi bloğu ve en altta bir veya daha fazla sürüm bilgisi bloğu (diğer diller ve/veya karakter kümeleri için). En üstteki bloktaki düzenlenebilir sayısal kutular ve seçilebilir açılan listeler bulunur. Alt bloklar yalnızca düzenlenebilir metin kutularına sahiptir.

> [!NOTE]
> **Sürüm bilgileri düzenleyicisini**kullanırken, birçok örnekte kaynağa özgü komutların kısayol menüsünü göstermek için sağ tıklayabilirsiniz. Örneğin, bir blok üst bilgi girişine işaret ederken ' yi seçerseniz, kısayol menüsü **Yeni sürüm engelleme bilgilerini** gösterir ve **Sürüm engelleme bilgisi komutlarını siler** .

## <a name="how-to"></a>Nasıl Yapılır

**Sürüm bilgileri Düzenleyicisi** şunları yapmanızı mümkün:

### <a name="to-edit-a-string-in-a-version-information-resource"></a>Sürüm bilgileri kaynağındaki bir dizeyi düzenlemek için

Öğeyi seçmek için bir kez seçtikten sonra yeniden oluşturmaya başlayın. Doğrudan **sürüm bilgileri** tablosunda veya [Özellikler penceresi](/visualstudio/ide/reference/properties-window)değişiklikler yapın. Yaptığınız değişiklikler her iki yerde de yansıtılacaktır.

`FILEFLAGS` **Sürüm bilgileri düzenleyicisinde**anahtar düzenlenirken,. RC dosyaları için **Özellikler** penceresinde **hata ayıklama**, **özel derleme**veya **özel derleme** özelliklerini ayarlayamıyorum:

   - **Sürüm bilgileri Düzenleyicisi** , `_DEBUG` derleme bayrağını temel alarak, kaynak `#ifdef` betikteki bir ile **hata ayıklama** özelliğini ayarlar.

  - `FILEFLAGS` Anahtarın sürüm bilgileri tablosunda ayarlanmış bir değeri varsa, anahtarın Özellikler penceresindeki karşılık gelen özel yapı özelliği doğru olacaktır. `Private Build` **Değer** boşsa, özelliği **false**olur. Benzer şekilde, **sürüm bilgileri** tablosundaki **özel derleme** anahtarı, `FILEFLAGS` anahtarın **özel derleme** özelliğine bağlıdır.

Dize bloğunun bilgi sırasını, **anahtar** ya da **değer** sütun başlıklarını seçerek sıralayabilirsiniz. Bu başlıklar, bilgileri seçilen sırayla otomatik olarak yeniden düzenler.

### <a name="to-add-version-information-for-another-language-new-version-info-block"></a>Başka bir dil için sürüm bilgileri eklemek için (yeni sürüm bilgi bloğu)

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources)içinde çift tıklayarak bir sürüm bilgisi kaynağını açın.

1. Sürüm bilgileri tablosuna sağ tıklayın ve **Yeni sürüm bilgi bloğu**' nu seçin.

   Bu komut, geçerli sürüm bilgileri kaynağına ek bilgi bloğu ekler ve [Özellikler penceresi](/visualstudio/ide/reference/properties-window)ilgili özelliklerini açar.

1. **Özellikler** penceresinde, yeni blobunun uygun dilini ve karakter kümesini seçin.

### <a name="to-delete-a-version-information-block"></a>Sürüm bilgisi bloğunu silmek için

1. [Kaynak görünümü](how-to-create-a-resource-script-file.md#create-resources)' deki simgesine çift tıklayarak sürüm bilgileri kaynağını açın.

1. Silmek istediğiniz blok üstbilgisine sağ tıklayın ve **sürüm bilgisi bloğunu Sil**' i seçin.

   Bu komut seçili üstbilgiyi siler ve sürüm bilgisinin geri kalanını bozulmadan bırakır. Eylemi geri alamazsınız.

### <a name="to-access-version-information-from-within-your-program"></a>Programınızın içinden sürüm bilgilerine erişmek için

Programınızın içinden sürüm bilgilerine erişmek istiyorsanız [GetFileVersionInfo](/windows/win32/api/winver/nf-winver-getfileversioninfow) Işlevini ve [VerQueryValue](/windows/win32/api/winver/nf-winver-verqueryvaluew) işlevini kullanın.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
[Menüler ve diğer kaynaklar](/windows/win32/menurc/resources)<br/>
[Sürüm bilgileri (Windows)](/windows/win32/menurc/version-information)
