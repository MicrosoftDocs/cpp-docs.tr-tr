---
title: Kayıt defteri betik oluşturma örnekleri
ms.date: 11/04/2016
helpviewer_keywords:
- scripting, examples
- registrar scripts [ATL]
- scripts, Registrar scripts
- registry, Registrar
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
ms.openlocfilehash: dffdd111d33d6fbd845e1534cdef1d5c8e1749d2
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57262941"
---
# <a name="registry-scripting-examples"></a>Kayıt defteri betik oluşturma örnekleri

Bu konudaki betik örnekleri, sistem kayıt defterine bir anahtar ekleyin, kayıt şirketi COM sunucusunun kaydedin ve birden çok ayrıştırma ağaçlarını belirtin göstermektedir.

## <a name="add-a-key-to-hkeycurrentuser"></a>HKEY_CURRENT_USER üzerine bir anahtar ekleyin

Aşağıdaki ayrıştırma ağacı tek bir anahtarı sistem kayıt defterine ekler basit bir komut dosyası gösterilmektedir. Özellikle, betik anahtar ekler `MyVeryOwnKey`, `HKEY_CURRENT_USER`. Ayrıca varsayılan dize değeri atar `HowGoesIt` yeni anahtarı:

```
HKEY_CURRENT_USER
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
```

Bu betik, birden çok alt şu şekilde tanımlamak için kolayca genişletilebilir:

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

Artık, bir alt komut dosyası ekler `HasASubkey`, `MyVeryOwnKey`. Bu alt anahtar hem de ekler `PrettyCool` alt (varsayılan değer `DWORD` 55 değerini) ve `ANameValue` adlandırılmış değeri (bir dize değeriyle `WithANamedValue`).

##  <a name="_atl_register_the_registrar_com_server"></a> Kayıt şirketi COM sunucusunu kaydetme

Aşağıdaki komut, kayıt şirketi COM sunucusunun kaydeder.

```
HKCR
{
    ATL.Registrar = s 'ATL Registrar Class'
    {
        CLSID = s '{44EC053A-400F-11D0-9DCD-00A0C90391D3}'
    }
    NoRemove CLSID
    {
        ForceRemove {44EC053A-400F-11D0-9DCD-00A0C90391D3} = s 'ATL Registrar Class'
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

Çalışma zamanında bu ayrıştırma ağacı ekler `ATL.Registrar` anahtarını `HKEY_CLASSES_ROOT`. Bu yeni anahtar için BT sonra:

- Belirtir `ATL Registrar Class` anahtarının varsayılan bir dize değeri olarak.

- Ekler `CLSID` bir alt olarak.

- Belirtir `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` için `CLSID`. (Bu değer, şirketinin ile kullanmak için CLSID `CoCreateInstance`.)

Bu yana `CLSID` olduğu paylaşılan, Unregister modunda kaldırılmamalıdır. Deyimi `NoRemove CLSID`, bu mu olduğunu belirten `CLSID` Unregister modunda yoksayılır ve kayıt modunda açıldığında gerekir.

`ForceRemove` Deyimi, bir anahtar ve tüm alt anahtarlarını anahtarı yeniden oluşturmadan önce kaldırarak temizlik işlevi sağlar. Bu anahtarlar adlarını değişip değişmediğini yararlı olabilir. Bu komut dosyası örnekte `ForceRemove` denetler `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` zaten mevcut. Aksi halde `ForceRemove`:

- Yinelemeli olarak siler `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` ve tüm alt anahtarlarını.

- Yeniden oluşturur `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.

- Ekler `ATL Registrar Class` için varsayılan dize değeri olarak `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.

Ayrıştırma ağacına artık iki yeni anahtarlarına ekler `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`. İlk anahtarı `ProgID`, ProgID: varsayılan bir dize değeri alır. İkinci anahtarı `InprocServer32`, varsayılan bir dize değeri, alır `%MODULE%`, diğer bir deyişle önişlemci değeri bölümünde açıklanan [değiştirilebilir parametreler kullanma (kaydedicinin ön işlemcisi)](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md), bu makalenin. `InprocServer32` Ayrıca, adlandırılmış bir değer alır `ThreadingModel`, bir dize değeriyle `Apartment`.

## <a name="specify-multiple-parse-trees"></a>Birden çok ayrıştırma ağaçlarını belirtin

Ayrıştırma ağacı birden fazla komut belirtmek için bir ağaç sonunda başka yerleştirin. Örneğin, aşağıdaki betiği anahtar ekler `MyVeryOwnKey`, her ikisi için de ayrıştırma ağaçlarını için `HKEY_CLASSES_ROOT` ve `HKEY_CURRENT_USER`:

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
> Bir kaydedici betikte belirteci boyutu 4K olan. (Bir belirteç sözdizimi tanınan herhangi bir öğenin içindir.) Önceki örnekte komut, `HKCR`, `HKEY_CURRENT_USER`, `'MyVeryOwnKey'`, ve `'HowGoesIt'` tüm belirteçlerin.

## <a name="see-also"></a>Ayrıca bkz.

[Kaydedici Betikleri Oluşturma](../atl/creating-registrar-scripts.md)
