---
title: Kayıt defteri komut dosyası örnekleri
ms.date: 11/04/2016
helpviewer_keywords:
- scripting, examples
- registrar scripts [ATL]
- scripts, Registrar scripts
- registry, Registrar
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
ms.openlocfilehash: 0e225ce28309aa619fd9436d8f4b93e60544e86c
ms.sourcegitcommit: 2bc15c5b36372ab01fa21e9bcf718fa22705814f
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/27/2020
ms.locfileid: "82168754"
---
# <a name="registry-scripting-examples"></a>Kayıt defteri komut dosyası örnekleri

Bu konudaki komut dosyası örnekleri, sistem kayıt defterine nasıl anahtar ekleneceğini, kaydedici COM sunucusunun nasıl kaydedeceğinizi ve birden çok ayrıştırma ağacının nasıl ekleneceğini göstermektedir.

## <a name="add-a-key-to-hkey_current_user"></a>HKEY_CURRENT_USER bir anahtar ekleyin

Aşağıdaki ayrıştırma ağacı, sistem kayıt defterine tek bir anahtar ekleyen basit bir komut dosyası gösterir. Özellikle, komut dosyası, `MyVeryOwnKey`' a anahtarını öğesine `HKEY_CURRENT_USER`ekler. Ayrıca, öğesinin `HowGoesIt` varsayılan dize değerini yeni anahtara atar:

```rgs
HKEY_CURRENT_USER
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
```

Bu betik, birden çok alt anahtarı şu şekilde tanımlamak üzere kolayca genişletilebilir:

```rgs
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

Şimdi, komut dosyası öğesine `HasASubkey` `MyVeryOwnKey`bir alt anahtar ekler. Bu alt anahtarda, `PrettyCool` hem alt anahtarı (varsayılan `DWORD` değer 55 ile) hem de `ANameValue` adlandırılmış değeri (dize değeri ile `WithANamedValue`) ekler.

## <a name="register-the-registrar-com-server"></a><a name="_atl_register_the_registrar_com_server"></a>Kaydedici COM sunucusunu kaydetme

Aşağıdaki betik, kaydedici COM sunucusunun kendisini kaydeder.

```rgs
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

Çalışma zamanında, bu ayrıştırma ağacı `ATL.Registrar` anahtarını öğesine `HKEY_CLASSES_ROOT`ekler. Bu yeni anahtara daha sonra:

- Anahtarın `ATL Registrar Class` varsayılan dize değerini belirtir.

- Alt `CLSID` anahtar olarak ekler.

- İçin `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` `CLSID`belirtir. (Bu değer, ile `CoCreateInstance`kullanmak için kayıt sahibinin CLSID değeridir.)

`CLSID` Paylaşıldığından, kayıt silme modunda kaldırılmamalıdır. , `NoRemove CLSID`, Bu, kayıt modunda açılması `CLSID` gerektiğini ve kayıt silme modunda yoksayılmayı belirterek bunu yapar.

`ForceRemove` İfade, anahtarı yeniden oluşturmadan önce bir anahtarı ve tüm alt anahtarlarını kaldırarak bir temizlik işlevi sağlar. Bu, alt anahtarların adları değiştiyse yararlı olabilir. Bu komut dosyası örneğinde, `ForceRemove` zaten mevcut olup `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` olmadığını denetler. Varsa `ForceRemove`:

- Tüm alt `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` anahtarlarını yinelemeli olarak siler.

- Yeniden oluşturur `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`.

- İçin `ATL Registrar Class` `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`varsayılan dize değeri olarak ekler.

Ayrıştırma ağacı artık ' ye `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`iki yeni alt anahtar ekliyor. İlk anahtar `ProgID`, ProgID olan varsayılan bir dize değerini alır. İkinci anahtar `InprocServer32`, bu makalenin `%MODULE%` [değiştirilebilen parametre (kaydedici 'nin ön işlemcisi) kullanılarak](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)bölümünde açıklanan bir Önişlemci değeri olan varsayılan bir dize değerini alır. `InprocServer32`Ayrıca `ThreadingModel`, dize değeri olan adlandırılmış bir değer alır `Apartment`.

## <a name="specify-multiple-parse-trees"></a>Birden fazla ayrıştırma ağacı belirtme

Bir betikte birden fazla ayrıştırma ağacı belirtmek için, diğerinin sonuna bir ağaç yerleştirebilirsiniz. Örneğin, aşağıdaki betik anahtarını `MyVeryOwnKey`ve `HKEY_CLASSES_ROOT` `HKEY_CURRENT_USER`için ayrıştırma ağaçlarına her ikisi için de ekler:

```rgs
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
> Bir kaydedici betiğinde, 4K en büyük belirteç boyutudur. (Belirteç söz diziminde tanınabilir bir öğedir.) Önceki `HKCR`komut dosyası örneğinde `HKEY_CURRENT_USER` `'MyVeryOwnKey'`,,, ve `'HowGoesIt'` tüm belirteçlerdir.

## <a name="see-also"></a>Ayrıca bkz.

[Kaydedici betikleri oluşturma](../atl/creating-registrar-scripts.md)
