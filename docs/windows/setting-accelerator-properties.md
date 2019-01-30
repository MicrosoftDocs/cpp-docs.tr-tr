---
title: Hızlandırıcı özelliklerini ayarlama (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- accelerator properties
- properties [C++], accelerator properties
- Type property
- Key property
- Modifier property
- VIRTKEY
- Key property
- ID property
ms.assetid: 0fce9156-3025-4e18-b034-e219a4c65812
ms.openlocfilehash: e1fac31635b7ccc09f9c184cf734fa4f7717cb97
ms.sourcegitcommit: 5beace7dcc6bf0e8b8cc96a930e7424f9daa05cb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 01/29/2019
ms.locfileid: "55232142"
---
# <a name="setting-accelerator-properties"></a>Hızlandırıcı özelliklerini ayarlama

Hızlandırıcı özelliklerini ayarlayabileceğiniz [Özellikler penceresi](/visualstudio/ide/reference/properties-window) dilediğiniz zaman. Ayrıca [Hızlandırıcı Düzenleyicisi](../windows/accelerator-editor.md) Hızlandırıcı tablosunda Hızlandırıcı özelliklerini değiştirmek için. Kullanılarak yapılan değişiklikleri **özellikleri** penceresi veya **hızlandırıcı** Düzenleyicisi sahip aynı sonucu: düzenlemeleri Hızlandırıcı tablosunda anında yansıtılır.

## <a name="id-property"></a>ID özelliği

**Kimliği** her Hızlandırıcı tablosu girişini program kodunda özelliğine başvuruyor. Bu giriş kullanıcı kısayol tuşunu ya da bir tuş bileşimi bastığında program alırsınız komut değerdir. (Hızlandırıcı tablosu kimliği menüsü kaynak kimliği ile aynı olduğu sürece) bir kısayol menü öğesi ile aynı yapmak için kimlikleri aynı yapın.

Her Hızlandırıcı kimliği için üç özellik vardır: **değiştiricisi** özelliği **anahtarı** özelliği ve **türü** özelliği.

## <a name="modifier-property"></a>Değiştirici özelliği

**Değiştiricisi** özelliği denetimi için kısayol tuş birleşimleri ayarlar.

> [!NOTE]
> İçinde **özellikleri** penceresi, bu özellik, üç ayrı görünür **Boole** özellikler, bunların tümü denetlenebilir bağımsız olarak: **Alt**, **Ctrl**, ve **Shift**.

İçin yasal girdileri verilmiştir **değiştiricisi** Hızlandırıcı tablosu özelliği:

   |Değer|Açıklama|
   |-----------|-----------------|
   |**Yok.**|Kullanıcı yalnızca **anahtar** değeri. Bu değer en etkili bir şekilde 026 aracılığıyla 001 ASCII/ANSI değerleri olarak yorumlanıp kullanılır ^ A-^ Z (**Ctrl + A** aracılığıyla **Ctrl + Z**).|
   |**Alt**|Kullanıcı gerekir basın **Alt** önce anahtar **anahtar** değeri.|
   |**CTRL**|Kullanıcı gerekir basın **Ctrl** önce anahtar **anahtar** değeri. ASCII türü geçerli değil.|
   |**Kaydırma**|Kullanıcı gerekir basın **Shift** önce anahtar **anahtar** değeri.|
   |**Ctrl + Alt**|Kullanıcı gerekir basın **Ctrl** anahtarı ve **Alt** önce anahtar **anahtar** değeri. ASCII türü geçerli değil.|
   |**CTRL + üst karakter**|Kullanıcı gerekir basın **Ctrl** anahtarı ve **Shift** önce anahtar **anahtar** değeri. ASCII türü geçerli değil.|
   |**Alt + üst karakter**|Kullanıcı gerekir basın **Alt** anahtarı ve **Shift** önce anahtar **anahtar** değeri. ASCII türü geçerli değil.|
   |**Ctrl + Alt + üst karakter**|Kullanıcı gerekir basın **Ctrl**, **Alt**, ve **Shift** önce **anahtar** değeri. ASCII türü geçerli değil.|

## <a name="key-property"></a>Anahtar özelliği

**Anahtar** özelliği Hızlandırıcı olarak kullanılacak gerçek anahtarı ayarlar.

İçin yasal girdileri verilmiştir **anahtar** Hızlandırıcı tablosu özelliği:

   |Değer|Açıklama|
   |-----------|-----------------|
   |0 ve 255 ondalık biçiminde arasında bir tamsayı.|Değer, değer ASCII veya ANSI şu şekilde işlenir olup olmadığını belirler:<br/><br/>-Tek basamaklı sayı her zaman ASCII veya ANSI değerleri olarak değil, karşılık gelen anahtar olarak yorumlanır.<br/>-1 ila 26, önünde sıfır ile zaman değerlerini olarak yorumlanır ^ A-^ alfabedeki ile basıldığında ASCII değeri temsil eden Z **Ctrl** tuşu basılı tutularak.<br/>-27-32 değerlerinden her zaman üç basamaklı ondalık değerler 032 aracılığıyla 027 olarak yorumlanır.<br/>-033 ile 255'den 0'ın öncesinde ya da ANSI değerleri olarak yorumlanmadı değerleri.|
   |Tek klavye karakter.|A - Z büyük harf veya sayı 0 - 9 ASCII veya sanal anahtar değerleri olabilir; başka bir karakter yalnızca ASCII'dir.|
   |Bir tek klavye karakter aralığı A - Z (yalnızca büyük), öncesinde bir şapka (^) (örneğin, ^ C).|İle basıldığında anahtarın ASCII değeri bu seçeneği girer **Ctrl** tuşu basılı tutularak.|
   |Herhangi bir geçerli sanal anahtar tanımlayıcı.|Hızlandırıcı tablosu açılan anahtar kutusunda standart sanal anahtarı tanımlayıcıları listesini içerir.|

> [!NOTE]
> ASCII değeri girerken değiştiricisi özellik seçenekleri sınırlıdır. Yalnızca denetim kullanılabilir için anahtar kullanımı **Alt** anahtarı.

> [!TIP]
> Hızlandırıcı tuşunu tanımlamak için başka bir yolu ise Hızlandırıcı tablosunda birden çok girişlere sağ tıklayın, seçin **sonraki anahtarı yazılan** kısayol menüsünden anahtarlar veya tuş birleşimleri birini klavyede tuşuna basın. **Sonraki anahtarı yazılan** komutu kullanılabilir ayrıca **Düzenle** menüsü.

## <a name="type-property"></a>Tür özelliği

**Türü** özelliği belirler Hızlandırıcı Kimliğiyle ilişkilendirilmiş kısayol tuş bileşimi bir ASCII/ANSI anahtar değeri veya bir sanal anahtar (VIRTKEY'e) birleşimi olarak yorumlanır.

- Varsa **türü** özelliktir ASCII, **değiştiricisi** özelliği být pouze parametry `None` veya `Alt`, veya kullanan bir Hızlandırıcı olabilir **Ctrl** (anahtar Belirtilen anahtarla koyarak bir `^`).

- Varsa **türü** özelliktir VIRTKEY'e, herhangi bir birleşimini `Modifier` ve `Key` değerleri geçerlidir.

> [!NOTE]
> Hızlandırıcı tablosu içine bir değer girin ve ASCII/ANSI, yalnızca tıklatın değerlendirilmesi bir değere sahip istiyorsanız **türü** açılır listeden seçin ASCII ve tablo girişi. Ancak, kullanırsanız **sonraki anahtarı yazılan** komut (**Düzenle** menüsü) belirtmek için `Key`, değiştirmeniz gerekir **türü** VIRTKEY'e özelliğine ASCII *önce* girme `Key` kod.

## <a name="requirements"></a>Gereksinimler

Win32

## <a name="see-also"></a>Ayrıca bkz.

[Hızlandırıcı Tablosunu Düzenleme](../windows/editing-in-an-accelerator-table.md)<br/>
[Önceden Tanımlanmış Hızlandırıcı Tuşları](../windows/predefined-accelerator-keys.md)<br/>
[Kaynak Düzenleyicileri](../windows/resource-editors.md)<br/>
