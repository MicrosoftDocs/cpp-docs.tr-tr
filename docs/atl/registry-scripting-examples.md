---
title: Kayıt Defteri Komut Dosyası Örnekleri
ms.date: 11/04/2016
helpviewer_keywords:
- scripting, examples
- registrar scripts [ATL]
- scripts, Registrar scripts
- registry, Registrar
ms.assetid: b6df80e1-e08b-40ee-9243-9b381b172460
ms.openlocfilehash: 7bcdb7076982e2f0bd08f4fd82bb45f21e61ef20
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81329334"
---
# <a name="registry-scripting-examples"></a>Kayıt Defteri Komut Dosyası Örnekleri

Bu konudaki komut dosyası örnekleri, sistem kayıt defterine nasıl bir anahtar ekleyeceğinizi, Registrar COM sunucusunu nasıl kaydedin ve birden çok ayrışma ağacını belirtin.

## <a name="add-a-key-to-hkey_current_user"></a>HKEY_CURRENT_USER Için Anahtar Ekle

Aşağıdaki ayrıştaz ağacı, sistem kayıt defterine tek bir anahtar ekleyen basit bir komut dosyasını gösterir. Özellikle, komut dosyası, `MyVeryOwnKey`' için `HKEY_CURRENT_USER`anahtar ekler. Ayrıca, yeni anahtara varsayılan `HowGoesIt` dize değerini atar:

```
HKEY_CURRENT_USER
{
    'MyVeryOwnKey' = s 'HowGoesIt'
}
```

Bu komut dosyası, birden çok alt tuşu aşağıdaki gibi tanımlamak için kolayca genişletilebilir:

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

Şimdi, komut dosyası bir `HasASubkey`alt `MyVeryOwnKey`anahtar ekler, için . Bu alt anahtara hem `PrettyCool` alt anahtar (varsayılan `DWORD` değeri 55) `ANameValue` hem de adlandırılmış değeri `WithANamedValue`(dize değeri yle) ekler.

## <a name="register-the-registrar-com-server"></a><a name="_atl_register_the_registrar_com_server"></a>Kayıt Şirketi COM Sunucusunu Kaydedin

Aşağıdaki komut dosyası Registrar COM sunucusunun kendisini kaydeder.

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

Çalışma zamanında, bu ayrışdıran `ATL.Registrar` ağaç `HKEY_CLASSES_ROOT`anahtarı ekler. Bu yeni anahtar için, o zaman:

- Anahtarın `ATL Registrar Class` varsayılan dize değeri olarak belirtir.

- Bir `CLSID` alt anahtar olarak ekler.

- Için `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` `CLSID`belirtir. (Bu değer, kayıt şirketinin CLSID'si ile birlikte `CoCreateInstance`kullanılır.)

Paylaşıldığından, `CLSID` Kayıt Dışı kaldırma modunda kaldırılmamalıdır. Açıklamada, `NoRemove CLSID`, kayıt modunda açılması `CLSID` gerektiğini ve Kayıt Dışı biçiminde göz ardı edilmesi gerektiğini belirterek bunu yapar.

İfade, `ForceRemove` anahtarı yeniden oluşturmadan önce bir anahtarı ve tüm alt anahtarlarını kaldırarak bir temizlik işlevi sağlar. Bu, alt tuşların adları değiştiyse yararlı olabilir. Bu komut dosyası `ForceRemove` örneği, zaten `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` var olup olmadığını görmek için denetler. Varsa, `ForceRemove`:

- Özyinelemeli olarak siler `{44EC053A-400F-11D0-9DCD-00A0C90391D3}` ve tüm alt anahtarları.

- Yeniden `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`oluşturur.

- Varsayılan `ATL Registrar Class` dize değeri `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`olarak ekler.

Ayrışdırma ağacı şimdi iki yeni `{44EC053A-400F-11D0-9DCD-00A0C90391D3}`alt tuşları ekler. İlk anahtar, `ProgID`ProgID olan varsayılan bir dize değeri alır. İkinci anahtar, `InprocServer32`, bu bölümde `%MODULE%`açıklanan bir önişlemci değeri, bu makalenin [Değiştirilebilir Parametreleri (Registrar's Preprocessor) kullanarak](../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)varsayılan bir dize değeri alır. `InprocServer32`ayrıca adlandırılmış bir `ThreadingModel`değer alır, `Apartment`bir dize değeri ile .

## <a name="specify-multiple-parse-trees"></a>Birden Çok Ayrışma Ağacı Belirtin

Bir komut dosyasında birden fazla ayrışma ağacı belirtmek için, bir ağacı diğerinin sonuna yerleştirmeniz yeterlidir. Örneğin, aşağıdaki komut dosyası, `MyVeryOwnKey`her ikisi `HKEY_CLASSES_ROOT` için ayrıştı `HKEY_CURRENT_USER`ağaçlarına anahtarı ekler ve:

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
> Registrar komut dosyasında, 4K en yüksek belirteç boyutudur. (Belirteç sözdiziminde tanınabilir bir öğedir.) Önceki komut dosyası `HKCR`örneğinde, , `HKEY_CURRENT_USER`, `'MyVeryOwnKey'`, ve `'HowGoesIt'` tüm belirteçleri vardır.

## <a name="see-also"></a>Ayrıca bkz.

[Kayıt Defteri Komut Dosyaları Oluşturma](../atl/creating-registrar-scripts.md)
