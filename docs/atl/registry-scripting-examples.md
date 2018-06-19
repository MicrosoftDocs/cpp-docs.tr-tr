---
title: Örnek komut dosyası kayıt defteri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- scripting, examples
- registrar scripts [ATL]
- scripts, Registrar scripts
- registry, Registrar
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4c192e8bec1d32dd7d7a7953e5da72a139c7520e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32361895"
---
# <a name="registry-scripting-examples"></a>Kayıt defteri komut dosyası yazma örnekleri
Bu konudaki komut dosyası örnekleri bir anahtar sistem kayıt defterine ekleyin, kayıt COM sunucuyu kaydetmek ve birden çok ayrıştırma ağacı belirtmek nasıl ekleyebileceğiniz gösterilmektedir.  
  
## <a name="add-a-key-to-hkeycurrentuser"></a>HKEY_CURRENT_USER anahtar ekleme  
 Aşağıdaki ayrıştırma ağacı sistem kayıt defterine tek bir anahtar ekler basit bir komut dosyası gösterilmektedir. Özellikle, betik anahtar ekler `MyVeryOwnKey`, `HKEY_CURRENT_USER`. Ayrıca varsayılan dize değeri atar `HowGoesIt` yeni anahtarı:  
  
```  
HKEY_CURRENT_USER  
{  
 'MyVeryOwnKey' = s 'HowGoesIt'  
}  
```  
  
 Bu komut, birden çok alt şu şekilde tanımlamak için kolayca genişletilebilir:  
  
```  
HKCU  
{  
 'MyVeryOwnKey' = s 'HowGoesIt'  
 {  
 'HasASubkey'  
 {  
 'PrettyCool' = d '55'  
    val 'ANameValue' = s 'WithANamedValue'  
 }  
 }  
}  
```  
  
 Şimdi, bir alt betik ekler `HasASubkey`, `MyVeryOwnKey`. Bu alt anahtar, her ikisi de ekler `PrettyCool` alt (varsayılan değer `DWORD` 55 değerini) ve `ANameValue` adlı değer (bir dize değeriyle `WithANamedValue`).  
  
##  <a name="_atl_register_the_registrar_com_server"></a> Kaydedici COM sunucusu kaydetme  
 Aşağıdaki komut dosyası kayıt COM sunucusu kaydeder.  
  
```  
HKCR  
{  
    ATL.Registrar = s 'ATL Registrar Class'  
 {  
    CLSID = s '{44EC053A-400F-11D0-9DCD-00A0C90391D3}'  
 }  
    NoRemove CLSID  
 {  
    ForceRemove {44EC053A-400F-11D0-9DCD-00A0C90391D3} = 
    s 'ATL Registrar Class'  
 {  
    ProgID = s 'ATL.Registrar'  
    InprocServer32 = s '%MODULE%'  
 {  
    val ThreadingModel = s 'Apartment'  
 }  
 }  
 }  
}  
```  
  
 Çalışma zamanında bu ayrıştırma ağacı ekler `ATL.Registrar` anahtarını `HKEY_CLASSES_ROOT`. Bu yeni anahtara BT sonra:  
  
-   Belirtir `ATL Registrar Class` anahtarın varsayılan dize değeri olarak.  
  
-   Ekler `CLSID` bir alt anahtarı olarak.  
  
-   Belirtir `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` için `CLSID`. (Bu değer kayıt şirketinin CLSID ile kullanılmak üzere `CoCreateInstance`.)  
  
 Bu yana `CLSID` olan paylaşılan, onu Unregister modunda kaldırılmaması gerekir. Deyimi `NoRemove CLSID`, bunu belirten tarafından yapar `CLSID` Unregister modunda göz ardı ve kayıt modunda açılmış gerekir.  
  
 `ForceRemove` Deyimi bir anahtarı ve tüm alt anahtarlarını anahtarı yeniden oluşturmadan önce kaldırarak kayıt tutma işlevi sağlar. Bu adları alt anahtarlarını değiştirdiyseniz yararlı olabilir. Bu komut dosyası örnekte `ForceRemove` denetler `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` zaten mevcut. Aşması durumunda `ForceRemove`:  
  
-   Yinelemeli siler `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` ve tüm alt anahtarlarını.  
  
-   Yeniden oluşturur `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.  
  
-   Ekler `ATL Registrar Class` varsayılan dize değeri olarak `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.  
  
 Ayrıştırma ağacı şimdi iki yeni anahtarlarına ekler `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`. İlk anahtar `ProgID`, ProgID: Varsayılan dize değerini alır. İkinci anahtar `InprocServer32`, varsayılan dize değerini alır `%MODULE%`, yani önişlemci değeri bölümünde açıklanan [kullanarak değiştirilebilir parametreler (kayıt şirketinizin önişlemci)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md), bu makalenin. `InprocServer32` Ayrıca adlandırılmış bir değer alır `ThreadingModel`, bir dize değeriyle `Apartment`.  
  
## <a name="specify-multiple-parse-trees"></a>Birden çok ayrıştırma ağacı belirtin  
 Bir komut dosyası birden fazla ayrıştırma ağacı belirtmek için bir ağaç sonunda başka yerleştirin. Örneğin, aşağıdaki komut anahtarı ekler `MyVeryOwnKey`, her ikisi için de ayrıştırma ağacı için `HKEY_CLASSES_ROOT` ve `HKEY_CURRENT_USER`:  
  
```  
HKCR  
{  
 'MyVeryOwnKey' = s 'HowGoesIt'  
}  
HKEY_CURRENT_USER  
{  
 'MyVeryOwnKey' = s 'HowGoesIt'  
}  
```  
  
> [!NOTE]
>  Kaydedici komut dosyasında, en büyük simge boyutu 4K'dır. (Bir belirteç herhangi tanınabilir sözdiziminde öğedir.) Önceki örnekte komut, `HKCR`, `HKEY_CURRENT_USER`, `'MyVeryOwnKey'`, ve `'HowGoesIt'` tüm belirteçleri.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Kaydedici Betikleri Oluşturma](../atl/creating-registrar-scripts.md)

