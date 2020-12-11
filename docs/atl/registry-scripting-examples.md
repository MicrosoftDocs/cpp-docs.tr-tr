---
description: 'Daha fazla bilgi edinin: kayıt defteri komut dosyası örnekleri'
title: Kayıt defteri komut dosyası örnekleri
ms.date: 11/04/2016
helpviewer_keywords:
- scripting, examples
- registrar scripts [ATL]
- scripts, Registrar scripts
- registry, Registrar
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
ms.openlocfilehash: 716aa69ed95c784079e72f9b785fedd8c07b0563
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157548"
---
# <a name="registry-scripting-examples"></a>Kayıt defteri komut dosyası örnekleri

Bu konudaki komut dosyası örnekleri, sistem kayıt defterine nasıl anahtar ekleneceğini, kaydedici COM sunucusunun nasıl kaydedeceğinizi ve birden çok ayrıştırma ağacının nasıl ekleneceğini göstermektedir.

## <a name="add-a-key-to-hkey_current_user"></a>HKEY_CURRENT_USER bir anahtar ekleyin

Aşağıdaki ayrıştırma ağacı, sistem kayıt defterine tek bir anahtar ekleyen basit bir komut dosyası gösterir. Özellikle, komut dosyası, ' a anahtarını `MyVeryOwnKey` öğesine ekler `HKEY_CURRENT_USER` . Ayrıca, öğesinin varsayılan dize değerini `HowGoesIt` Yeni anahtara atar:

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

Şimdi, komut dosyası öğesine bir alt anahtar ekler `HasASubkey` `MyVeryOwnKey` . Bu alt anahtarda, hem `PrettyCool` alt anahtarı (varsayılan `DWORD` değer 55 ile) hem de `ANameValue` adlandırılmış değeri (dize değeri ile `WithANamedValue` ) ekler.

## <a name="register-the-registrar-com-server"></a><a name="_atl_register_the_registrar_com_server"></a> Kaydedici COM sunucusunu kaydetme

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

Çalışma zamanında, bu ayrıştırma ağacı `ATL.Registrar` anahtarını öğesine ekler `HKEY_CLASSES_ROOT` . Bu yeni anahtara daha sonra:

- `ATL Registrar Class`Anahtarın varsayılan dize değerini belirtir.

- `CLSID`Alt anahtar olarak ekler.

- `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`İçin belirtir `CLSID` . (Bu değer, ile kullanmak için kayıt sahibinin CLSID değeridir `CoCreateInstance` .)

`CLSID`Paylaşıldığından, kayıt silme modunda kaldırılmamalıdır. , `NoRemove CLSID` , Bu, `CLSID` kayıt modunda açılması gerektiğini ve kayıt silme modunda yoksayılmayı belirterek bunu yapar.

`ForceRemove`İfade, anahtarı yeniden oluşturmadan önce bir anahtarı ve tüm alt anahtarlarını kaldırarak bir temizlik işlevi sağlar. Bu, alt anahtarların adları değiştiyse yararlı olabilir. Bu komut dosyası örneğinde, `ForceRemove` zaten mevcut olup olmadığını denetler `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` . Varsa `ForceRemove` :

- `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`Tüm alt anahtarlarını yinelemeli olarak siler.

- Yeniden oluşturur `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` .

- `ATL Registrar Class`İçin varsayılan dize değeri olarak ekler `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` .

Ayrıştırma ağacı artık ' ye iki yeni alt anahtar ekliyor `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` . İlk anahtar, `ProgID` ProgID olan varsayılan bir dize değerini alır. İkinci anahtar, `InprocServer32` `%MODULE%` Bu makalenin [değiştirilebilen parametre (kaydedici 'nin ön işlemcisi) kullanılarak](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)bölümünde açıklanan bir Önişlemci değeri olan varsayılan bir dize değerini alır. `InprocServer32` Ayrıca `ThreadingModel` , dize değeri olan adlandırılmış bir değer alır `Apartment` .

## <a name="specify-multiple-parse-trees"></a>Birden fazla ayrıştırma ağacı belirtme

Bir betikte birden fazla ayrıştırma ağacı belirtmek için, diğerinin sonuna bir ağaç yerleştirebilirsiniz. Örneğin, aşağıdaki betik anahtarını `MyVeryOwnKey` ve için ayrıştırma ağaçlarına her ikisi için de ekler `HKEY_CLASSES_ROOT` `HKEY_CURRENT_USER` :

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
> Bir kaydedici betiğinde, 4K en büyük belirteç boyutudur. (Belirteç söz diziminde tanınabilir bir öğedir.) Önceki komut dosyası örneğinde,, `HKCR` , `HKEY_CURRENT_USER` `'MyVeryOwnKey'` ve `'HowGoesIt'` Tüm belirteçlerdir.

## <a name="see-also"></a>Ayrıca bkz.

[Kaydedici betikleri oluşturma](../atl/creating-registrar-scripts.md)
