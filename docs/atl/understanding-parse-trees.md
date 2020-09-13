---
title: ATL kaydedici ve ayrıştırma ağaçları
ms.date: 11/04/2016
helpviewer_keywords:
- parse trees
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
ms.openlocfilehash: ff74ff879e757a569232ff19244d3f7598063465
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2020
ms.locfileid: "90040294"
---
# <a name="understanding-parse-trees"></a>Ayrıştırma ağaçlarını anlama

Kaydedici betiğinizdeki bir veya daha fazla ayrıştırma ağacı tanımlayabilirsiniz, burada her bir ayrıştırma ağacının aşağıdaki biçimi vardır:

> \<root key>{\<registry expression>}+

burada:

> \<root key> :: = HKEY_CLASSES_ROOT \| HKEY_CURRENT_USER \|\
> &emsp;HKEY_LOCAL_MACHINE \| HKEY_USERS \|\
> &emsp;HKEY_PERFORMANCE_DATA \| HKEY_DYN_DATA \|\
> &emsp;HKEY_CURRENT_CONFIG \| HKCR \| HKCU \|\
> &emsp;HKLM \| HKU \| hkpd \| hkdd \| HKCC

> \<registry expression>::= \<Add Key> \|\<Delete Key>

> \<Add Key>:: = \[ **ForceRemove** \| **NoRemove** \| **Val**] \<Key Name> [ \<Key Value> ] [{ \<Add Key> }]

> \<Delete Key> :: = **Delete**\<Key Name>

> \<Key Name> ::= **'**\<AlphaNumeric>+**'**

> \<AlphaNumeric> :: = *herhangi bir karakter null değil, yanı ASCII 0*

> \<Key Value> ::= \<Key Type>\<Key Name>

> \<Key Type> :: = **s** \| **d**

> \<Key Value> ::= **'**\<AlphaNumeric>**'**

> [!NOTE]
> `HKEY_CLASSES_ROOT` ve `HKCR` eşdeğerdir; `HKEY_CURRENT_USER` `HKCU` eşdeğerdir; ve bu şekilde devam eder.

Bir ayrıştırma ağacı öğesine birden çok anahtar ve alt anahtar ekleyebilir \<root key> . Bunu yaparken, çözümleyici tüm alt anahtarlarını ayrıştırmayı tamamlayana kadar bir alt anahtarın tanıtıcısını açık tutar. Bu yaklaşım, aşağıdaki örnekte görüldüğü gibi, her seferinde tek bir anahtarda kullanılandan daha etkilidir:

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

Burada, kaydedici başlangıçta açılır (oluşturur) `HKEY_CLASSES_ROOT\MyVeryOwnKey` . Sonra `MyVeryOwnKey` bir alt anahtarı olduğunu görür. Anahtarı ' a kapatmak yerine, `MyVeryOwnKey` kaydedici tanıtıcıyı korur ve `HasASubKey` Bu üst tutamacı kullanarak (oluşturur) açar. (Üst tanıtıcı açık olmadığında sistem kayıt defteri daha yavaş olabilir.) Bu nedenle, `HKEY_CLASSES_ROOT\MyVeryOwnKey` `HasASubKey` üst öğe olarak birlikte açma ve sonra açma `MyVeryOwnKey` , açma `MyVeryOwnKey` , kapatma `MyVeryOwnKey` ve sonra açma özelliğinden daha hızlıdır `MyVeryOwnKey\HasASubKey` .

## <a name="see-also"></a>Ayrıca bkz.

[Kaydedici betikleri oluşturma](../atl/creating-registrar-scripts.md)
