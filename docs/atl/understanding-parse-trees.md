---
title: "ATL Kaydedicisi ve ayrıştırma ağacı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords: parse trees
ms.assetid: 668ce2dd-a1c3-4ca0-8135-b25267cb6a85
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 091ad40625c85f465e3989dd2dff790c630f6538
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="understanding-parse-trees"></a>Anlama ayrıştırma ağacı
Her ayrıştırma ağacı aşağıdaki biçime sahip olduğu kayıt komut dosyanıza, bir veya daha fazla ayrıştırma ağacı tanımlayabilirsiniz:  
  
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
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>  
 [<Key Value>][{<Add Key>}]  
<Delete Key> ::= Delete<Key Name>  
<Key Name> ::= '<AlphaNumeric>+'  
<AlphaNumeric> ::= any character not NULL, i.e. ASCII 0  
<Key Value> ::== <Key Type><Key Name>  
<Key Type> ::= s | d  
<Key Value> ::= '<AlphaNumeric>'  
```  
  
> [!NOTE]
> `HKEY_CLASSES_ROOT`ve `HKCR` eşdeğer; `HKEY_CURRENT_USER` ve `HKCU` eşdeğerlidir; ve vb..  
  
 Ayrıştırma ağacı birden çok anahtarlar ve alt anahtarlar için ekleyebilirsiniz \<kök anahtarı >. Ayrıştırıcının tüm alt anahtarlarını ayrıştırma tamamlanana kadar bunu yaparken, bir alt anahtarının tanıtıcı açık tutar. Bu yaklaşım, aşağıdaki örnekte görüldüğü gibi bir kerede tek bir anahtar işletim değerinden daha verimli olur:  
  
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
  
 Burada, kayıt şirketi başlangıçta açar (oluşturur) `HKEY_CLASSES_ROOT\MyVeryOwnKey`. Bunun ardından, görür `MyVeryOwnKey` bir alt anahtarı vardır. Anahtar kapatmak yerine `MyVeryOwnKey`, kayıt şirketi tanıtıcı korur ve açar (oluşturur) `HasASubKey` bu üst tanıtıcısını kullanarak. (Üst tanıtıcı yok açık olduğunda sistem kayıt defteri yavaş olabilir.) Bu nedenle, açma `HKEY_CLASSES_ROOT\MyVeryOwnKey` ve açarak `HasASubKey` ile `MyVeryOwnKey` üst açılış daha hızlıdır gibi `MyVeryOwnKey`, kapatma `MyVeryOwnKey`ve ardından açma `MyVeryOwnKey\HasASubKey`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaydedici betikleri oluşturma](../atl/creating-registrar-scripts.md)

