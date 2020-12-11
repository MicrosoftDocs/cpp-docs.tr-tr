---
description: 'Daha fazla bilgi edinin: Backus-Naur form (BNF) söz dizimini anlama'
title: ATL kaydedici ve Backus-Naur form (BNF) sözdizimi
ms.date: 05/14/2019
helpviewer_keywords:
- BNF notation
- Backus-Naur form (BNF) syntax
ms.assetid: 994bbef0-9077-4aa8-bdfe-b7e830af9acc
ms.openlocfilehash: 7f392d442c4d43865faf9e788f8bf69288673398
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157353"
---
# <a name="understanding-backus-naur-form-bnf-syntax"></a>Backus-Naur formu (BNF) söz dizimini anlama

ATL kaydedicisi tarafından kullanılan betikler bu konuda, aşağıdaki tabloda gösterilen gösterimi kullanan BNF söz dizimi kullanılarak açıklanmıştır.

|Kural/simge|Anlamı|
|------------------------|-------------|
|::=|Eşdeğer|
|&#124;|VEYA|
|X +|Bir veya daha fazla xs.|
|\[Sayı|X isteğe bağlıdır. İsteğe bağlı sınırlayıcılar,] ile belirtilir \[ .|
|Herhangi bir **kalın** metin|Dize sabit değeri.|
|Herhangi bir *italik* metin|Dize sabit değerini oluşturma.|

Yukarıdaki tabloda gösterildiği gibi, kaydedici betikleri dize sabit değerleri kullanır. Bu değerler, betiğinizdeki görünmesi gereken gerçek metinlerdir. Aşağıdaki tabloda, ATL Kaydedici komut dosyasında kullanılan dize sabit değerleri açıklanmaktadır.

|Dize sabit değeri|Eylem|
|--------------------|------------|
|**ForceRemove**|Bir sonraki anahtarı (varsa) tamamen kaldırır ve yeniden oluşturur.|
|**NoRemove**|Kayıt silme sırasında sonraki anahtarı kaldırmaz.|
|**Acil**|`<Key Name>`Aslında adlandırılmış bir değer olduğunu belirtir.|
|**Silme**|Kayıt sırasında bir sonraki anahtarı siler.|
|**s**|Sonraki değerin bir dize (REG_SZ) olduğunu belirtir.|
|**d**|Sonraki değerin bir DWORD (REG_DWORD) olduğunu belirtir.|
|**m**|Bir sonraki değerin çok dizeli (REG_MULTI_SZ) olduğunu belirtir.|
|**kenarı**|Sonraki değerin bir ikili değer (REG_BINARY) olduğunu belirtir.|

## <a name="bnf-syntax-examples"></a>BNF sözdizimi örnekleri

Bir ATL kaydedici betiğinin gösterimi ve dize değişmez değerlerinin nasıl çalıştığını anlamanıza yardımcı olacak birkaç sözdizimi örneği aşağıda verilmiştir.

### <a name="syntax-example-1"></a>Sözdizimi örneği 1

> \<registry expression> ::= \<Add Key>

`registry expression`ile eşdeğer olduğunu belirtir `Add Key` .

### <a name="syntax-example-2"></a>Sözdizimi örneği 2

> \<registry expression> ::= \<Add Key> | \<Delete Key>

`registry expression`ya da ile eşdeğer olduğunu belirtir `Add Key` `Delete Key` .

### <a name="syntax-example-3"></a>Sözdizimi örneği 3

> \<Key Name> ::= '\<AlphaNumeric>+'

`Key Name`bir veya daha fazla değere eşdeğer bir `AlphaNumeric` değer belirtir.

### <a name="syntax-example-4"></a>Söz dizimi örnek 4

> \<Add Key>:: = [**ForceRemove**  |  **NoRemove**  |  **Val**]\<Key Name>

' `Add Key` nin `Key Name` , ve dize değişmez `ForceRemove` `NoRemove` `val` değerlerinin isteğe bağlı olduğunu belirtir.

### <a name="syntax-example-5"></a>Söz dizimi örnek 5

> \<AlphaNumeric> :: = *herhangi bir karakter null değil, diğer bir deyişle, ASCII 0*

`AlphaNumeric`null olmayan herhangi bir karakterle eşdeğer bir değer belirtir.

### <a name="syntax-example-6"></a>Sözdizimi örneği 6

```rgs
val 'testmulti' = m 'String 1\0String 2\0'
```

anahtar adının `testmulti` ve ' den oluşan çok dizeli bir değer olduğunu belirtir `String 1` `String 2` .

### <a name="syntax-example-7"></a>Sözdizimi örneği 7

```rgs
val 'testhex' = d '&H55'
```

anahtar adının `testhex` onaltılı 55 (ondalık 85) olarak ayarlanmış BIR DWORD değeri olduğunu belirtir. Bu biçim, Visual Basic belirtiminde bulunan **&H** gösterimine uyar.

## <a name="see-also"></a>Ayrıca bkz.

[Kaydedici betikleri oluşturma](../atl/creating-registrar-scripts.md)
