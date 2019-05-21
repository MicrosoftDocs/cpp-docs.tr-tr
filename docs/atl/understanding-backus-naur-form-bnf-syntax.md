---
title: ATL Kaydedicisi ve Backus-Naur form (BNF) söz dizimi
ms.date: 05/14/2019
helpviewer_keywords:
- BNF notation
- Backus-Naur form (BNF) syntax
ms.assetid: 994bbef0-9077-4aa8-bdfe-b7e830af9acc
ms.openlocfilehash: 77f0fa6fef8e517e5714d1da6c61d0e310e0718c
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65709162"
---
# <a name="understanding-backus-naur-form-bnf-syntax"></a>Backus-Naur form (BNF) söz dizimini anlama

ATL kayıt şirketi tarafından kullanılan betikler aşağıdaki tabloda gösterilen gösterimi kullanan BNF söz dizimini kullanarak bu konuda açıklanmıştır.

|Kuralı/sembol|Açıklama|
|------------------------|-------------|
|::=|Eşdeğer|
|&#124;|VEYA|
|X +|Bir veya daha fazla Xs.|
|\[X]|X isteğe bağlıdır. İsteğe bağlı ayırıcılar tarafından gösterilen \[].|
|Tüm **kalın** metin|Bir dize sabit değeri.|
|Tüm *italik* metin|Dize sabit değeri oluşturmak nasıl.|

Kaydedici betikleri, yukarıdaki tabloda gösterildiği gibi dize sabit değerleri kullanın. Bu değerler betiğinizde görünmesi gereken gerçek metin. Bir ATL Kaydedicisi betiğinde kullanılan dize değişmez değerleri aşağıdaki tabloda açıklanmaktadır.

|Dize sabit değeri|Eylem|
|--------------------|------------|
|**ForceRemove**|Sonraki anahtarı (varsa) tamamen kaldırır ve yeniden oluşturur.|
|**NoRemove**|Sonraki anahtarı sırasında Unregister kaldırmaz.|
|**VAL**|Belirten `<Key Name>` aslında bir adlandırılmış değerdir.|
|**Delete**|Sonraki anahtarı, kayıt sırasında siler.|
|**s**|Sonraki değeri (REG_SZ) bir dize belirtir.|
|**d**|Sonraki değeri bir DWORD (REG_DWORD) olduğunu belirtir.|
|**m**|Sonraki değeri bir multistring (REG_MULTI_SZ) olduğunu belirtir.|
|**b**|Sonraki değeri bir ikili değeri (REG_BINARY) olduğunu belirtir.|

## <a name="bnf-syntax-examples"></a>BNF sözdizimi örnekleri

Gösterim ve dize değişmez değerleri bir ATL Kaydedicisi betikte nasıl çalıştığını anlamanıza yardımcı olması için birkaç söz dizimi örnekleri aşağıda verilmiştir.

### <a name="syntax-example-1"></a>Sözdizimi örneği 1

```
<registry expression> ::= <Add Key>
```

belirten `registry expression` eşdeğerdir `Add Key`.

### <a name="syntax-example-2"></a>Sözdizimi örneği 2

```
<registry expression> ::= <Add Key> | <Delete Key>
```

belirten `registry expression` ya da eşdeğerine `Add Key` veya `Delete Key`.

### <a name="syntax-example-3"></a>Sözdizimi örneği 3

```
<Key Name> ::= '<AlphaNumeric>+'
```

belirten `Key Name` bir veya daha fazla eşdeğerdir `AlphaNumerics`.

### <a name="syntax-example-4"></a>4 sözdizimi örneği

```
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>
```

belirten `Add Key` eşdeğerdir `Key Name`ve dize değişmez değerleri, `ForceRemove`, `NoRemove`, ve `val`, isteğe bağlıdır.

### <a name="syntax-example-5"></a>5 sözdizimi örneği

```
<AlphaNumeric> ::= any character not NULL, that is, ASCII 0
```

belirten `AlphaNumeric` herhangi NULL karakter olmayan için eşdeğerdir.

### <a name="syntax-example-6"></a>6 sözdizimi örneği

```
val 'testmulti' = m 'String 1\0String 2\0'
```

belirten anahtar adı `testmulti` oluşan bir çok dizeli değer `String 1` ve `String 2`.

### <a name="syntax-example-7"></a>7 sözdizimi örneği

```
val 'testhex' = d '&H55'
```

belirten anahtar adı `testhex` bir DWORD değeri, onaltılık 55 (ondalık 85) ayarlanır. Bu biçim aynılarını için Not **& H** gösterimi olarak Visual Basic belirtiminde bulunamadı.

## <a name="see-also"></a>Ayrıca bkz.

[Kaydedici Betikleri Oluşturma](../atl/creating-registrar-scripts.md)