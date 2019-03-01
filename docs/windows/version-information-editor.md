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
ms.openlocfilehash: 8382371acfd423f8c6864e816b0357e3ef11718e
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210984"
---
# <a name="version-information-editor-c"></a>Sürüm bilgileri Düzenleyicisi (C++)

Sürüm bilgileri, şirket ve ürün kimliği, bir ürün sürüm numarasını ve telif hakkı ve ticari marka bildirimini oluşur. İle **sürüm bilgileri Düzenleyicisi**, oluşturma ve sürüm bilgileri kaynağında depolanan bu verileri korumak. Sürüm bilgileri kaynağında bir uygulama tarafından gerekli değildir, ancak uygulamayı tanımlayan bilgileri toplamak için kullanışlı bir yerdir. Sürüm bilgileri de API'leri kurulum tarafından kullanılır.

> [!NOTE]
> Windows standart VS_VERSION_INFO adlı yalnızca bir sürümü kaynak sağlamaktır.

Sürüm bilgileri kaynağında bir üst bloğu ve bir veya daha fazla alt blokları vardır: tek bir sabit bilgi bloğu üst ve alt (diğer diller ve/veya karakter kümesi için) bir veya daha fazla sürüm bilgi bloğu. Üst blok düzenlenebilir bir sayısal kutusu hem seçilebilir aşağı açılan listesi vardır. Alt bloklar yalnızca düzenlenebilir metin kutuları sahip.

> [!NOTE]
> Kullanırken **sürüm bilgileri Düzenleyicisi**, çoğu durumda bir kaynağa özgü komutların kısayol menüsünü görüntülemek için sağ tıklayabilirsiniz. Örneğin, bir blok üstbilgisi girişine işaret ederken seçin, kısayol menüsünü gösterir **yeni sürüm blok bilgisi** ve **sürüm blok bilgisi silme** komutları.

## <a name="how-to"></a>Nasıl Yapılır

**Sürüm bilgileri Düzenleyicisi** sağlar:

### <a name="to-edit-a-string-in-a-version-information-resource"></a>Sürüm bilgileri kaynağında dize düzenleme

Düzenlemeye başlamak için daha sonra tekrar seçmek için bir kez öğesi seçin. Değişiklik doğrudan **sürüm bilgisi** tablo veya [Özellikler penceresi](/visualstudio/ide/reference/properties-window). Her iki yerde de yaptığınız değişiklikler yansıtılır.

Düzenleme yaparken `FILEFLAGS` anahtarını **sürüm bilgileri Düzenleyicisi**, dikkat edin, ayarlayamıyor **hata ayıklama**, **özel derleme**, veya **özel yapı**  özelliklerinde **özellikleri** penceresi .rc dosyası için:

   - **Sürüm bilgileri Düzenleyicisi** ayarlar **hata ayıklama** özelliğiyle bir `#ifdef` kaynak kodda temel alarak `_DEBUG` bayrağı oluşturun.

  - Varsa `Private Build` anahtara sahip bir **değer** kümesinde **sürüm bilgisi** tablosundaki karşılık gelen **özel derleme** özelliğinde **özellikleri**  penceresi `FILEFLAGS` anahtar olacaktır **True**. Varsa **değer** olan özelliği boş olacaktır **False**. Benzer şekilde, **özel yapı** anahtarını **sürüm bilgisi** tablo için bağlı **özel yapı** özelliği `FILEFLAGS` anahtarı.

Bilgi dizesi blok bir dizi ya da seçerek sıralayabilirsiniz **anahtarı** veya **değer** sütun başlıkları. Bu başlıkları seçili sıra bilgilerini otomatik olarak yeniden düzenleyin.

### <a name="to-add-version-information-for-another-language-new-version-info-block"></a>(Yeni sürüm bilgi bloğu) başka bir dil için sürüm bilgileri ekleme

1. Sürüm bilgileri kaynağında çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. İçinde sürüm bilgileri tabloya sağ tıklayıp seçin **yeni sürüm bilgi bloğu**.

   Bu komut bir ek bilgi bloğu geçerli sürüm bilgileri kaynağında için ekler ve karşılık gelen özelliklerini açar [Özellikler penceresi](/visualstudio/ide/reference/properties-window).

1. İçinde **özellikleri** penceresinde ilgili dili seçin ve karakter kümesi için yeni bir blok.

### <a name="to-delete-a-version-information-block"></a>Sürüm bilgi bloğu silmek için

1. Sürüm bilgileri kaynağında simgeye çift tıklayarak açın [kaynak görünümü](../windows/resource-view-window.md).

1. Seçin ve silmek istediğiniz blok başlığına sağ tıklayarak **sürüm bilgi bloğunu silme**.

   Bu komut, seçilen üst bilgi siler ve sürüm bilgileri geri kalanını dokunmaz. Eylemi geri alamazsınız.

### <a name="to-access-version-information-from-within-your-program"></a>Programınızdan sürüm bilgilerine erişmek için

Programınızdan sürüm bilgilerine erişmek istiyorsanız, kullanmanız [GetFileVersionInfo](/windows/desktop/api/winver/nf-winver-getfileversioninfoa) işlevi ve [VerQueryValue](/windows/desktop/api/winver/nf-winver-verqueryvaluea) işlevi.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca Bkz.

[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
<!--
[Menus and Other Resources](https://msdn.microsoft.com/library/windows/desktop/ms632583.aspx)<br/>
[Version Information (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)-->
