---
description: 'Daha fazla bilgi edinin: sürüm bilgileri Düzenleyicisi (C++)'
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
ms.openlocfilehash: e639db4fd0ec8ac6291be452c000a23246bac662
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283231"
---
# <a name="version-information-editor-c"></a>Sürüm bilgileri Düzenleyicisi (C++)

Sürüm bilgileri şirket ve ürün kimliği, ürün sürüm numarası ve telif hakkı ve ticari marka bildirimiyle oluşur. **Sürüm bilgileri Düzenleyicisi** ile, sürüm bilgileri kaynağında saklanan bu verileri oluşturur ve korursunuz. Sürüm bilgisi kaynağı bir uygulama için gerekli değildir, ancak uygulamayı tanımlayan bilgileri toplamak yararlı bir yerdir. Sürüm bilgileri, kurulum API 'Leri tarafından da kullanılır.

> [!NOTE]
> Windows Standard 'da, VS_VERSION_INFO adlı yalnızca bir sürüm kaynağı vardır.

Sürüm bilgileri kaynağında bir üst blok ve bir veya daha fazla alt blok bulunur: en üstteki tek bir sabit bilgi bloğu ve en altta bir veya daha fazla sürüm bilgisi bloğu (diğer diller ve/veya karakter kümeleri için). En üstteki bloktaki düzenlenebilir sayısal kutular ve seçilebilir açılan listeler bulunur. Alt bloklar yalnızca düzenlenebilir metin kutularına sahiptir.

> [!NOTE]
> **Sürüm bilgileri düzenleyicisini** kullanırken, birçok örnekte kaynağa özgü komutların kısayol menüsünü göstermek için sağ tıklayabilirsiniz. Örneğin, bir blok üst bilgi girişine işaret ederken ' yi seçerseniz, kısayol menüsü **Yeni sürüm engelleme bilgilerini** gösterir ve **Sürüm engelleme bilgisi komutlarını siler** .

## <a name="how-to"></a>Nasıl yapılır

**Sürüm bilgileri Düzenleyicisi** şunları yapmanızı mümkün:

### <a name="to-edit-a-string-in-a-version-information-resource"></a>Sürüm bilgileri kaynağındaki bir dizeyi düzenlemek için

Öğeyi seçmek için bir kez seçtikten sonra yeniden oluşturmaya başlayın. Doğrudan **sürüm bilgileri** tablosunda veya [Özellikler penceresi](/visualstudio/ide/reference/properties-window)değişiklikler yapın. Yaptığınız değişiklikler her iki yerde de yansıtılacaktır.

`FILEFLAGS` **Sürüm bilgileri düzenleyicisinde** anahtar düzenlenirken,. RC dosyaları Için **Özellikler** penceresinde **hata ayıklama**, **özel derleme** veya **özel derleme** özelliklerini ayarlayamıyorum:

- **Sürüm bilgileri Düzenleyicisi** ,  `#ifdef` derleme bayrağını temel alarak, kaynak betikteki bir ile hata ayıklama özelliğini ayarlar `_DEBUG` .

- `Private Build`Anahtarın **sürüm bilgileri** tablosunda ayarlanmış bir **değeri** varsa, anahtarın **Özellikler** penceresindeki karşılık gelen **özel yapı** özelliği `FILEFLAGS` **doğru** olacaktır. **Değer** boşsa, özelliği **false** olur. Benzer şekilde, **sürüm bilgileri** tablosundaki **özel derleme** anahtarı, anahtarın **özel derleme** özelliğine bağlıdır `FILEFLAGS` .

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

[Kaynak düzenleyicileri](../windows/resource-editors.md)<br/>
[Menüler ve diğer kaynaklar](/windows/win32/menurc/resources)<br/>
[Sürüm bilgileri (Windows)](/windows/win32/menurc/version-information)
