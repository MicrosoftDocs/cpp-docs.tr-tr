---
title: Kayıt defteri makroları
ms.date: 08/19/2019
f1_keywords:
- atlcom/ATL::_ATL_STATIC_REGISTRY
- atlcom/ATL::DECLARE_LIBID
- atlcom/ATL::DECLARE_NO_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY_APPID_RESOURCEID
- atlcom/ATL::DECLARE_REGISTRY_RESOURCE
- atlcom/ATL::DECLARE_REGISTRY_RESOURCEID
helpviewer_keywords:
- registry, ATL macros
ms.assetid: 3ee041da-c63b-42a4-89cf-2a4b2a6f81ae
ms.openlocfilehash: dac1c187bae0eb55b954fc02cd4fb4c981f272f4
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834524"
---
# <a name="registry-macros"></a>Kayıt defteri makroları

Bu makrolar yararlı tür kitaplığı ve kayıt defteri olanakları tanımlar.

|Ad|Açıklama|
|-|-|
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|ATL.DLL bağımlılığı önlemek için nesnenizin kayıt kodunun nesne içinde olmasını istediğinizi belirtir.|
|[DECLARE_LIBID](#declare_libid)|ATL 'nin tür kitaplığının *libıd* 'sini alması için bir yol sağlar.|
|[DECLARE_NO_REGISTRY](#declare_no_registry)|Varsayılan ATL kaydını önler.|
|[DECLARE_REGISTRY](#declare_registry)|Sistem kayıt defterindeki ana nesnenin girişini girer veya kaldırır.|
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|*AppID*'yi otomatik olarak kaydetmek için gereken bilgileri belirtir.|
|[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)|Adlandırılmış kaynağı bulur ve kayıt defteri betiğini onun içinde çalıştırır.|
|[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)|KIMLIK numarası tarafından tanımlanan kaynağı bulur ve kayıt defteri betiğini bunun içinde çalıştırır.|

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlcom. h

## <a name="_atl_static_registry"></a><a name="_atl_static_registry"></a> _ATL_STATIC_REGISTRY

ATL.DLL bağımlılığı önlemek için nesnenizin kayıt kodunun nesnede olmasını istediğinizi belirten bir simge.

```
#define _ATL_STATIC_REGISTRY
```

### <a name="remarks"></a>Açıklamalar

ATL_STATIC_REGISTRY tanımladığınızda aşağıdaki kodu kullanmanız gerekir:

[!code-cpp[NVC_ATL_EventHandlingSample#5](../../atl/codesnippet/cpp/registry-macros_1.cpp)]

## <a name="declare_libid"></a><a name="declare_libid"></a> DECLARE_LIBID

ATL 'nin tür kitaplığının *libıd* 'sini alması için bir yol sağlar.

```
DECLARE_LIBID( libid )
```

### <a name="parameters"></a>Parametreler

*Kitaplık kimliği*<br/>
Tür kitaplığının GUID 'SI.

### <a name="remarks"></a>Açıklamalar

Türetilmiş bir sınıfta DECLARE_LIBID kullanın `CAtlModuleT` .

### <a name="example"></a>Örnek

Öznitelikle bulunmayan sihirbaz tarafından oluşturulan ATL projelerinin bu makroyu kullanma örneği olacaktır.

## <a name="declare_no_registry"></a><a name="declare_no_registry"></a> DECLARE_NO_REGISTRY

Bu makronun göründüğü sınıf için herhangi bir varsayılan ATL kaydını önlemek istiyorsanız DECLARE_NO_REGISTRY kullanın.

```
DECLARE_NO_REGISTRY()
```

## <a name="declare_registry"></a><a name="declare_registry"></a> DECLARE_REGISTRY

Standart sınıf kaydını sistem kayıt defterine girer veya sistem kayıt defterinden kaldırır.

```
DECLARE_REGISTRY(
    class,
    pid,
    vpid,
    nid,
    flags )
```

### <a name="parameters"></a>Parametreler

*sınıfı*<br/>
'ndaki Geriye dönük uyumluluk için eklenmiştir.

*Kişisel*<br/>
'ndaki Sürüme özgü bir program tanımlayıcısı olan bir LPCTSTR.

*Address*<br/>
'ndaki Sürümden bağımsız program tanımlayıcısı olan bir LPCTSTR.

*NID*<br/>
'ndaki Programın açıklaması olarak kullanılacak kayıt defterindeki kaynak dizesinin bir dizini olan bir UINT.

*bayraklar*<br/>
'ndaki Kayıt defterinde programın iş parçacığı modelini içeren bir DWORD. Şu değerlerden biri olmalıdır: THREADFLAGS_APARTMENT, THREADFLAGS_BOTH veya AUTPRXFLAG.

### <a name="remarks"></a>Açıklamalar

Standart kayıt CLSID, program KIMLIĞI, sürümden bağımsız program KIMLIĞI, açıklama dizesi ve iş parçacığı modelinden oluşur.

ATL sınıf ekleme Sihirbazı 'nı kullanarak bir nesne veya denetim oluşturduğunuzda, sihirbaz komut dosyası tabanlı kayıt defteri desteğini otomatik olarak uygular ve [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) makrosunu dosyalarınıza ekler. Betik tabanlı kayıt defteri desteğini istemiyorsanız, bu makroyu DECLARE_REGISTRY değiştirmeniz gerekir. DECLARE_REGISTRY, yukarıda açıklanan beş temel anahtarı yalnızca kayıt defterine ekler. Kayıt defterine diğer anahtarlar eklemek için el ile kod yazmalısınız.

## <a name="declare_registry_appid_resourceid"></a><a name="declare_registry_appid_resourceid"></a> DECLARE_REGISTRY_APPID_RESOURCEID

*AppID*'yi otomatik olarak kaydetmek için gereken bilgileri belirtir.

```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid,
    appid )
```

### <a name="parameters"></a>Parametreler

*RESID*<br/>
*AppID*ile ilgili bilgileri içeren. rgs dosyasının kaynak kimliği.

*AppID*<br/>
BIR GUıD.

### <a name="remarks"></a>Açıklamalar

Türetilmiş bir sınıfta DECLARE_REGISTRY_APPID_RESOURCEID kullanın `CAtlModuleT` .

### <a name="example"></a>Örnek

Sınıf kodu ekleme Sihirbazı ile ATL projelerine eklenen sınıfların bu makroyu kullanma örneği olacaktır.

## <a name="declare_registry_resource"></a><a name="declare_registry_resource"></a> DECLARE_REGISTRY_RESOURCE

Kayıt defteri dosyasını içeren adlandırılmış kaynağı alır ve sistem kayıt defterine nesneleri girmek ya da sistem kayıt defterinden kaldırmak için betiği çalıştırır.

```
DECLARE_REGISTRY_RESOURCE( x )
```

### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Kaynağınızın dize tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

ATL Proje Sihirbazı 'nı kullanarak bir nesne veya denetim oluşturduğunuzda, sihirbaz otomatik olarak betik tabanlı kayıt defteri desteğini uygular ve DECLARE_REGISTRY_RESOURCE benzer [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) makrosunu dosyalarınıza ekler.

En iyileştirilmiş kayıt defteri erişimi için ATL kayıt defteri bileşeni (kaydedici) ile statik olarak bağlantı oluşturabilirsiniz. Kayıt koduna statik olarak bağlanmak için, *pch. h* dosyanıza aşağıdaki satırı ekleyin (Visual Studio 2017 ve önceki sürümlerde*stdadfx. h* ):

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

Çalışma zamanında ATL 'nin değiştirme değerlerini yerine koymak istiyorsanız, DECLARE_REGISTRY_RESOURCE veya DECLARE_REGISTRY_RESOURCEID makrosunu belirtmeyin. Bunun yerine, `_ATL_REGMAP_ENTRIES` her girdinin çalışma zamanında yer tutucuyu değiştirecek bir değerle eşleştirilmiş bir değişken yer tutucusu içerdiği bir yapı dizisi oluşturun. Ardından, diziyi geçirerek [CAtlModule:: UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) veya [CAtlModule:: UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources)öğesini çağırın. Bu, yapılardaki değiştirme değerlerinin tümünü kayıt `_ATL_REGMAP_ENTRIES` sahibinin eşleme haritasına ekler.

Değiştirilebilir parametreler ve betik oluşturma hakkında daha fazla bilgi için, [atl kayıt defteri bileşeni (kaydedici)](../../atl/atl-registry-component-registrar.md)makalesine bakın.

## <a name="declare_registry_resourceid"></a><a name="declare_registry_resourceid"></a> DECLARE_REGISTRY_RESOURCEID

Bir dize adı yerine, kaynağı tanımlamak için sihirbaz tarafından oluşturulan bir UINT kullanması hariç [DECLARE_REGISTRY_RESOURCE](#declare_registry_resource) aynıdır.

```
DECLARE_REGISTRY_RESOURCEID( x )
```

### <a name="parameters"></a>Parametreler

*x*<br/>
'ndaki Sihirbaz tarafından oluşturulan kaynağınızın tanıtıcısı.

### <a name="remarks"></a>Açıklamalar

ATL Proje Sihirbazı 'nı kullanarak bir nesne veya denetim oluşturduğunuzda, sihirbaz otomatik olarak betik tabanlı kayıt defteri desteğini uygular ve DECLARE_REGISTRY_RESOURCEID makrosunu dosyalarınıza ekler.

En iyileştirilmiş kayıt defteri erişimi için ATL kayıt defteri bileşeni (kaydedici) ile statik olarak bağlantı oluşturabilirsiniz. Kayıt koduna statik olarak bağlanmak için aşağıdaki satırı *stdadfx. h* dosyanıza (Visual Studio 2019 ve üzeri sürümlerde*pch. h* ) ekleyin:

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

Çalışma zamanında ATL 'nin değiştirme değerlerini yerine koymak istiyorsanız, DECLARE_REGISTRY_RESOURCE veya DECLARE_REGISTRY_RESOURCEID makrosunu belirtmeyin. Bunun yerine, `_ATL_REGMAP_ENTRIES` her girdinin çalışma zamanında yer tutucuyu değiştirecek bir değerle eşleştirilmiş bir değişken yer tutucusu içerdiği bir yapı dizisi oluşturun. Ardından, diziyi geçirerek [CAtlModule:: UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) veya [CAtlModule:: UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources)öğesini çağırın. Bu, yapılardaki değiştirme değerlerinin tümünü kayıt `_ATL_REGMAP_ENTRIES` sahibinin eşleme haritasına ekler.

Değiştirilebilir parametreler ve betik oluşturma hakkında daha fazla bilgi için, [atl kayıt defteri bileşeni (kaydedici)](../../atl/atl-registry-component-registrar.md)makalesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
