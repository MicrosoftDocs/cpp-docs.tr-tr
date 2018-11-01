---
title: ATL Kaydedicisi ve ayrıştırma ağaçlarını
ms.date: 11/04/2016
helpviewer_keywords:
- parse trees
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
ms.openlocfilehash: 11625ebda2e84d4a738a2d54e849e3406a5c4f70
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50510883"
---
# <a name="understanding-parse-trees"></a>Ayrıştırma ağaçlarını anlama

Bir veya daha fazla ayrıştırma ağaçlarını her ayrıştırma ağacı aşağıdaki biçime sahip olduğu kayıt şirketi betiğinizi içinde tanımlayabilirsiniz:

```
<root key>{<registry expression>}+
```

burada:

```
<root key> ::= HKEY_CLASSES_ROOT | HKEY_CURRENT_USER |
    HKEY_LOCAL_MACHINE | HKEY_USERS |
    HKEY_PERFORMANCE_DATA | HKEY_DYN_DATA |
    HKEY_CURRENT_CONFIG | HKCR | HKCU |
    HKLM | HKU | HKPD | HKDD | HKCC
<registry expression> ::= <Add Key> | <Delete Key>
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name> [<Key Value>][{<Add Key>}]
<Delete Key> ::= Delete<Key Name>
<Key Name> ::= '<AlphaNumeric>+'
<AlphaNumeric> ::= any character not NULL, i.e. ASCII 0
<Key Value> ::== <Key Type><Key Name>
<Key Type> ::= s | d
<Key Value> ::= '<AlphaNumeric>'
```

> [!NOTE]
> `HKEY_CLASSES_ROOT` ve `HKCR` eşdeğerdir; `HKEY_CURRENT_USER` ve `HKCU` eşdeğer; ve bu şekilde.

Bir ayrıştırma ağacı birden çok anahtar ve anahtarlarına ekleyebilirsiniz \<kök anahtarı >. Ayrıştırıcının tüm alt anahtarlarını ayrıştırma işlemi tamamlanana kadar bunu yaparken, bir alt anahtarının tanıtıcı açık tutar. Bu yaklaşım, aşağıdaki örnekte görüldüğü gibi bir kerede tek bir anahtar işletim değerinden daha verimli olur:

```
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

Burada, kayıt şirketi başlangıçta açar (oluşturur) `HKEY_CLASSES_ROOT\MyVeryOwnKey`. Ardından, gördüğünde `MyVeryOwnKey` bir alt anahtarı vardır. Anahtar kapatmak yerine `MyVeryOwnKey`, kayıt şirketi tanıtıcı korur ve açar (oluşturur) `HasASubKey` bu üst tanıtıcı kullanma. (Hiçbir üst tanıtıcı açık olduğunda sistem kayıt defterine daha yavaş olabilir.) Bu nedenle, açma `HKEY_CLASSES_ROOT\MyVeryOwnKey` ve açarak `HasASubKey` ile `MyVeryOwnKey` üst açılış daha hızlı olduğundan `MyVeryOwnKey`, kapanış `MyVeryOwnKey`ve ardından açarak `MyVeryOwnKey\HasASubKey`.

## <a name="see-also"></a>Ayrıca Bkz.

[Kaydedici Betikleri Oluşturma](../atl/creating-registrar-scripts.md)

