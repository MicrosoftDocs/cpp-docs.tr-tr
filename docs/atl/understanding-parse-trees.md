---
title: ATL kaydedici ve ayrıştırma ağaçları
ms.date: 11/04/2016
helpviewer_keywords:
- parse trees
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
ms.openlocfilehash: de2cea9b0e7b7c62236f708f9aa8217eaa5df51d
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168702"
---
# <a name="understanding-parse-trees"></a>Ayrıştırma ağaçlarını anlama

Kaydedici betiğinizdeki bir veya daha fazla ayrıştırma ağacı tanımlayabilirsiniz, burada her bir ayrıştırma ağacının aşağıdaki biçimi vardır:

> \<kök anahtar> {\<kayıt defteri ifadesi>} +

burada:

> \<kök anahtar>:: = HKEY_CLASSES_ROOT | HKEY_CURRENT_USER | \
> &nbsp;&nbsp;&nbsp;&nbsp;HKEY_LOCAL_MACHINE | HKEY_USERS | \
> &nbsp;&nbsp;&nbsp;&nbsp;HKEY_PERFORMANCE_DATA | HKEY_DYN_DATA | \
> &nbsp;&nbsp;&nbsp;&nbsp;HKEY_CURRENT_CONFIG | HKCR | HKCU | \
> &nbsp;&nbsp;&nbsp;&nbsp;HKLM | HKU | HKPD | HKDD | HKCC

> \<kayıt defteri ifadesi>:: \<= anahtar> Ekle | \<Anahtar> Sil

> \<Anahtar Ekle>:: = [**ForceRemove** | **NoRemove** | **Val**]\<anahtar adı> [\<anahtar değer>] [{\<anahtar ekleme>}]

> \<Delete Key>:: = anahtar adını **Sil**\<>

> \<Anahtar adı>:: = **'**\<alfasayısal>+**'**

> \<Alfasayısal>:: = *herhangi bir karakter null değil, yanı ASCII 0*

> \<Anahtar değeri>:: = \<anahtar türü>\<anahtar adı>

> \<Anahtar türü>:: = **s** | **d**

> \<Anahtar değeri>:: = **'**\<alfasayısal>**'**

> [!NOTE]
> `HKEY_CLASSES_ROOT`ve `HKCR` eşdeğerdir; `HKEY_CURRENT_USER` ve `HKCU` eşdeğerdir; vb.

Bir ayrıştırma ağacı, \<kök anahtara> birden çok anahtar ve alt anahtar ekleyebilir. Bunu yaparken, çözümleyici tüm alt anahtarlarını ayrıştırmayı tamamlayana kadar bir alt anahtarın tanıtıcısını açık tutar. Bu yaklaşım, aşağıdaki örnekte görüldüğü gibi, her seferinde tek bir anahtarda kullanılandan daha etkilidir:

```rgs
HKEY_CLASSES_ROOT
{
    'MyVeryOwnKey'
    {
        'HasASubKey'
        {
            'PrettyCool'
        }
    }
}
```

Burada, kaydedici başlangıçta açılır (oluşturur) `HKEY_CLASSES_ROOT\MyVeryOwnKey`. Sonra bir alt anahtarı `MyVeryOwnKey` olduğunu görür. Anahtarı `MyVeryOwnKey`' a kapatmak yerine, kaydedici tanıtıcıyı korur ve bu üst tutamacı kullanarak (oluşturur) `HasASubKey` açar. (Üst tanıtıcı açık olmadığında sistem kayıt defteri daha yavaş olabilir.) Bu nedenle, `HKEY_CLASSES_ROOT\MyVeryOwnKey` üst öğe olarak `HasASubKey` birlikte `MyVeryOwnKey` açma ve sonra açma `MyVeryOwnKey`, açma, kapatma `MyVeryOwnKey`ve sonra açma `MyVeryOwnKey\HasASubKey`özelliğinden daha hızlıdır.

## <a name="see-also"></a>Ayrıca bkz.

[Kaydedici betikleri oluşturma](../atl/creating-registrar-scripts.md)
