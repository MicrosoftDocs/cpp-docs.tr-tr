---
title: ATL kaydedici ve Backus-Naur form (BNF) sözdizimi
ms.date: 05/14/2019
helpviewer_keywords:
- BNF notation
- Backus-Naur form (BNF) syntax
ms.assetid: 994bbef0-9077-4aa8-bdfe-b7e830af9acc
ms.openlocfilehash: 0f07a39863b586d524d060dc3df7117e2c930b3e
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168715"
---
# <a name="understanding-backus-naur-form-bnf-syntax"></a>Backus-Naur formu (BNF) söz dizimini anlama

ATL kaydedicisi tarafından kullanılan betikler bu konuda, aşağıdaki tabloda gösterilen gösterimi kullanan BNF söz dizimi kullanılarak açıklanmıştır.

|Kural/simge|Anlamı|
|------------------------|-------------|
|::=|Eşdeğer|
|&#124;|OR|
|X +|Bir veya daha fazla xs.|
|\[Sayı|X isteğe bağlıdır. İsteğe bağlı sınırlayıcılar,] \[ile belirtilir.|
|Herhangi bir **kalın** metin|Dize sabit değeri.|
|Herhangi bir *italik* metin|Dize sabit değerini oluşturma.|

Yukarıdaki tabloda gösterildiği gibi, kaydedici betikleri dize sabit değerleri kullanır. Bu değerler, betiğinizdeki görünmesi gereken gerçek metinlerdir. Aşağıdaki tabloda, ATL Kaydedici komut dosyasında kullanılan dize sabit değerleri açıklanmaktadır.

|Dize sabit değeri|Eylem|
|--------------------|------------|
|**ForceRemove**|Bir sonraki anahtarı (varsa) tamamen kaldırır ve yeniden oluşturur.|
|**NoRemove**|Kayıt silme sırasında sonraki anahtarı kaldırmaz.|
|**Acil**|Aslında adlandırılmış `<Key Name>` bir değer olduğunu belirtir.|
|**Sil**|Kayıt sırasında bir sonraki anahtarı siler.|
|**malar**|Sonraki değerin bir dize (REG_SZ) olduğunu belirtir.|
|**TID**|Sonraki değerin bir DWORD (REG_DWORD) olduğunu belirtir.|
|**m**|Bir sonraki değerin çok dizeli (REG_MULTI_SZ) olduğunu belirtir.|
|**kenarı**|Sonraki değerin bir ikili değer (REG_BINARY) olduğunu belirtir.|

## <a name="bnf-syntax-examples"></a>BNF sözdizimi örnekleri

Bir ATL kaydedici betiğinin gösterimi ve dize değişmez değerlerinin nasıl çalıştığını anlamanıza yardımcı olacak birkaç sözdizimi örneği aşağıda verilmiştir.

### <a name="syntax-example-1"></a>Sözdizimi örneği 1

> \<kayıt defteri ifadesi>:: \<= anahtar> Ekle

`registry expression` ile `Add Key`eşdeğer olduğunu belirtir.

### <a name="syntax-example-2"></a>Sözdizimi örneği 2

> \<kayıt defteri ifadesi>:: \<= anahtar> Ekle | \<Anahtar> Sil

`registry expression` `Add Key` ya `Delete Key`da ile eşdeğer olduğunu belirtir.

### <a name="syntax-example-3"></a>Sözdizimi örneği 3

> \<Anahtar adı>:: = '\<alfasayısal>+ '

`Key Name` bir veya daha fazla `AlphaNumeric` değere eşdeğer bir değer belirtir.

### <a name="syntax-example-4"></a>Söz dizimi örnek 4

> \<Anahtar> ekleyin:: = [**ForceRemove** | **NoRemove** | **Val**]\<anahtar adı>

`Add Key` ' `Key Name`nin, `ForceRemove`ve `NoRemove` `val`dize değişmez değerlerinin isteğe bağlı olduğunu belirtir.

### <a name="syntax-example-5"></a>Söz dizimi örnek 5

> \<Alfasayısal>:: = *hiçbir karakter null değil, diğer bir deyişle, ASCII 0*

`AlphaNumeric` null olmayan herhangi bir karakterle eşdeğer bir değer belirtir.

### <a name="syntax-example-6"></a>Sözdizimi örneği 6

```rgs
val 'testmulti' = m 'String 1\0String 2\0'
```

anahtar adının `testmulti` `String 1` ve ' `String 2`den oluşan çok dizeli bir değer olduğunu belirtir.

### <a name="syntax-example-7"></a>Sözdizimi örneği 7

```rgs
val 'testhex' = d '&H55'
```

anahtar adının `testhex` onaltılı 55 (ondalık 85) olarak AYARLANMıŞ bir DWORD değeri olduğunu belirtir. Bu biçim, Visual Basic belirtiminde bulunan **&H** gösterimine uyar.

## <a name="see-also"></a>Ayrıca bkz.

[Kaydedici betikleri oluşturma](../atl/creating-registrar-scripts.md)
