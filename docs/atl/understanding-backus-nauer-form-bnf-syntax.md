---
title: "ATL Kaydedicisi ve Backus Nauer Form (BNF) sözdizimini | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- BNF notation
- Backus Nauer Form (BNF) syntax
ms.assetid: 994bbef0-9077-4aa8-bdfe-b7e830af9acc
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 01d364313420c0a950f8eba222e3ae020fbd86cf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="understanding-backus-nauer-form-bnf-syntax"></a>Backus Nauer Form (BNF) sözdizimi anlama
ATL Kaydedicisi tarafından kullanılan komut aşağıdaki tabloda gösterilen gösterimi kullanan BNF sözdizimini kullanarak bu konuda açıklanmaktadır.  
  
|Kuralı/simgesi|Açıklama|  
|------------------------|-------------|  
|`::=`|Eşdeğer|  
|`&#124;`|VEYA|  
|`X+`|Bir veya daha fazla `X`s.|  
|`[X]`|`X`isteğe bağlıdır. İsteğe bağlı ayırıcısı tarafından gösterilen `[]`.|  
|Tüm **kalın** metin|Bir dize sabit değeri.|  
|Tüm *italik* metin|Dize sabit değeri oluşturma.|  
  
 Önceki tabloda belirtildiği gibi Kaydedici betikleri dize değişmez değerleri kullanın. Bu komut dosyanıza görünmesi gereken gerçek metin değerleridir. ATL Kaydedicisi komut dosyasında kullanılan dize değişmez değerleri aşağıdaki tabloda açıklanmaktadır.  
  
|Dize değişmez değeri|Eylem|  
|--------------------|------------|  
|**ForceRemove**|(Varsa) sonraki anahtarı tamamen kaldırır ve yeniden oluşturur.|  
|**NoRemove**|Sonraki anahtarı sırasında Unregister kaldırmaz.|  
|**VAL**|Belirleyen `<Key Name>` gerçekten adlandırılmış bir değer.|  
|**Sil**|Sonraki anahtarı kayıt sırasında siler.|  
|**s**|Sonraki değeri bir dize olduğunu belirtir (**REG_SZ**).|  
|**d**|Sonraki değer olduğunu belirten bir **DWORD** (**REG_DWORD**).|  
|**m**|Sonraki değeri bir multistring olduğunu belirtir (**REG_MULTI_SZ**).|  
|**b**|Sonraki değeri bir ikili değer olduğunu belirtir (**REG_BINARY**).|  
  
## <a name="bnf-syntax-examples"></a>BNF sözdizimi örnekleri  
 ATL Kaydedicisi komut dosyasında gösterimi ve dize değişmez değerleri nasıl çalıştığını anlamanıza yardımcı olması için birkaç sözdizimi örnekleri aşağıda verilmiştir.  
  
### <a name="syntax-example-1"></a>Sözdizimi örneği 1  
  
```  
<registry expression> ::= <Add Key>  
```  
  
 belirleyen `registry expression` eşdeğerdir `Add Key`.  
  
### <a name="syntax-example-2"></a>Sözdizimi örneği 2  
  
```  
<registry expression> ::= <Add Key> | <Delete Key>  
```  
  
 belirleyen `registry expression` ya da eşdeğer bir gruba `Add Key` veya `Delete Key`.  
  
### <a name="syntax-example-3"></a>Sözdizimi örneği 3  
  
```  
<Key Name> ::= '<AlphaNumeric>+'  
```  
  
 belirleyen `Key Name` bir veya daha fazla eşdeğerdir `AlphaNumerics`.  
  
### <a name="syntax-example-4"></a>Sözdizimi örneği 4  
  
```  
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
```  
  
 belirleyen `Add Key` eşdeğerdir `Key Name`ve dize değişmez değerleri `ForceRemove`, `NoRemove`, ve `val`, isteğe bağlıdır.  
  
### <a name="syntax-example-5"></a>Sözdizimi örneği 5  
  
```  
<AlphaNumeric> ::= any character not NULL, that is, ASCII 0  
```  
  
 belirleyen `AlphaNumeric` herhangi Değersiz olmayan tüm karakterler için eşdeğerdir.  
  
### <a name="syntax-example-6"></a>Sözdizimi örneği 6  
  
```  
val 'testmulti' = m 'String 1\0String 2\0'  
```  
  
 belirleyen anahtar adı `testmulti` bir çok dizeli değer oluşan `String 1` ve `String 2`.  
  
### <a name="syntax-example-7"></a>Sözdizimi örneği 7  
  
```  
val 'testhex' = d '&H55'  
```  
  
 belirleyen anahtar adı `testhex` olan bir **DWORD** değerini onaltılık 55 (ondalık 85) ayarlayın. Bu biçim aynılarını için Not **& H** gösterimi olarak Visual Basic belirtiminde bulundu.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaydedici Betikleri Oluşturma](../atl/creating-registrar-scripts.md)

