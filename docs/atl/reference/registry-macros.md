---
title: Kayıt Defteri Makroları
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
ms.openlocfilehash: fd012b4300f4cd72cdc9ab363b770ac1dbefa06e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81326037"
---
# <a name="registry-macros"></a>Kayıt Defteri Makroları

Bu makrolar yararlı tür kitaplığı ve kayıt defteri olanaklarını tanımlar.

|||
|-|-|
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|ATL bağımlılığını önlemek için nesnenizin kayıt kodunun nesnede olmasını istediğinizi belirtir. Dll.|
|[DECLARE_LIBID](#declare_libid)|ATL'nin tür kitaplığı *libid'ini* elde etmesi için bir yol sağlar.|
|[DECLARE_NO_REGISTRY](#declare_no_registry)|Varsayılan ATL kaydını önler.|
|[DECLARE_REGISTRY](#declare_registry)|Ana nesnenin girişini sistem kayıt defterine girer veya kaldırır.|
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|*Appid'i*otomatik olarak kaydetmek için gereken bilgileri belirtir.|
|[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)|Adlandırılmış kaynağı bulur ve içindeki kayıt defteri komut dosyasını çalıştırın.|
|[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)|Kimlik numarasıyla tanımlanan kaynağı bulur ve içindeki kayıt defteri komut dosyasını çalıştırın.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

## <a name="_atl_static_registry"></a><a name="_atl_static_registry"></a>_ATL_STATIC_REGISTRY

ATL bağımlılığını önlemek için nesnenizin kayıt kodunun nesnede olmasını istediğinizi belirten bir simge. Dll.

```
#define _ATL_STATIC_REGISTRY
```

### <a name="remarks"></a>Açıklamalar

ATL_STATIC_REGISTRY tanımlarken aşağıdaki kodu kullanmalısınız:

[!code-cpp[NVC_ATL_EventHandlingSample#5](../../atl/codesnippet/cpp/registry-macros_1.cpp)]

## <a name="declare_libid"></a><a name="declare_libid"></a>DECLARE_LIBID

ATL'nin tür kitaplığı *libid'ini* elde etmesi için bir yol sağlar.

```
DECLARE_LIBID( libid )
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
Tür kitaplığın GUID'i.

### <a name="remarks"></a>Açıklamalar

DECLARE_LIBID türetilmiş bir `CAtlModuleT`sınıfta kullanın.

### <a name="example"></a>Örnek

Atfedilen olmayan sihirbaz tarafından oluşturulan ATL projeleri bu makroyu kullanarak bir örneğe sahip olacaktır.

## <a name="declare_no_registry"></a><a name="declare_no_registry"></a>DECLARE_NO_REGISTRY

Bu makronun göründüğü sınıf için varsayılan ATL kaydını önlemek istiyorsanız DECLARE_NO_REGISTRY kullanın.

```
DECLARE_NO_REGISTRY()
```

## <a name="declare_registry"></a><a name="declare_registry"></a>DECLARE_REGISTRY

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

*sınıf*<br/>
[içinde] Geriye dönük uyumluluk için dahildir.

*Pıd*<br/>
[içinde] Sürüme özel bir program tanımlayıcısı olan bir LPCTSTR.

*vpid*<br/>
[içinde] Sürümden bağımsız bir program tanımlayıcısı olan bir LPCTSTR.

*Nıd*<br/>
[içinde] Programın açıklaması olarak kullanmak için kayıt defterinde kaynak dizebir dizin bir UINT.

*bayraklar*<br/>
[içinde] Kayıt defterinde programın iş parçacığı modelini içeren bir DWORD. Aşağıdaki değerlerden biri olmalıdır: THREADFLAGS_APARTMENT, THREADFLAGS_BOTH veya AUTPRXFLAG.

### <a name="remarks"></a>Açıklamalar

Standart kayıt CLSID, program kimliği, sürümden bağımsız program kimliği, açıklama dizesi ve iş parçacığı modelinden oluşur.

ATL Sınıf Ekle Sihirbazı'nı kullanarak bir nesne veya denetim oluşturduğunuzda, sihirbaz komut dosyası tabanlı kayıt defteri desteğini otomatik olarak uygular ve [dosyalarınıza DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) makroekler. Komut dosyası tabanlı kayıt defteri desteği istemiyorsanız, bu makroyu DECLARE_REGISTRY değiştirmeniz gerekir. DECLARE_REGISTRY yalnızca yukarıda açıklanan beş temel anahtarı kayıt defterine ekler. Kayıt defterine diğer anahtarları eklemek için kod el ile yazmanız gerekir.

## <a name="declare_registry_appid_resourceid"></a><a name="declare_registry_appid_resourceid"></a>DECLARE_REGISTRY_APPID_RESOURCEID

*Appid'i*otomatik olarak kaydetmek için gereken bilgileri belirtir.

```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid,
    appid )
```

### <a name="parameters"></a>Parametreler

*Resid*<br/>
.rgs dosyasının *appid*hakkında bilgi içeren kaynak kimliği.

*Appıd*<br/>
Bİr REHBER.

### <a name="remarks"></a>Açıklamalar

DECLARE_REGISTRY_APPID_RESOURCEID türetilmiş bir `CAtlModuleT`sınıfta kullanın.

### <a name="example"></a>Örnek

Sınıf Ekle kodu sihirbazı ile ATL projelerine eklenen sınıflar, bu makroyu kullanma örneğine sahip olur.

## <a name="declare_registry_resource"></a><a name="declare_registry_resource"></a>DECLARE_REGISTRY_RESOURCE

Kayıt defteri dosyasını içeren adlandırılmış kaynağı alır ve komut dosyasını sistem kayıt defterine nesneleri girmek veya sistem kayıt defterinden kaldırmak için çalıştırır.

```
DECLARE_REGISTRY_RESOURCE( x )
```

### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Kaynağınızın dize tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

ATL Project Sihirbazı'nı kullanarak bir nesne veya denetim oluşturduğunuzda, sihirbaz komut dosyası tabanlı kayıt defteri desteğini otomatik olarak uygular ve dosyalarınıza DECLARE_REGISTRY_RESOURCE benzer [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) makrosu ekler.

En iyi duruma getirilmiş kayıt defteri erişimi için ATL Kayıt Defteri Bileşeni (Registrar) ile statik olarak bağlantı kurabilirsiniz. Kayıt Şirketi koduna statik olarak bağlanmak için *pch.h* dosyanıza (Visual Studio 2017 ve önceki*stdafx.h)* aşağıdaki satırı ekleyin:

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

ATL'nin çalışma zamanında değiştirme değerlerini değiştirmesini istiyorsanız, DECLARE_REGISTRY_RESOURCE veya DECLARE_REGISTRY_RESOURCEID makrosu belirtmeyin. Bunun yerine, her `_ATL_REGMAP_ENTRIES` girişin çalışma zamanında yer tutucuyu değiştirmek için bir değerle eşleştirilmiş değişken bir yer tutucu içerdiği bir dizi yapı oluşturun. Sonra [CAtlModule arayın::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) veya [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), dizi geçen. Bu, `_ATL_REGMAP_ENTRIES` yapılardaki tüm değiştirme değerlerini Kayıt Defteri'nin değiştirme haritasına ekler.

Değiştirilebilir parametreler ve komut dosyası hakkında daha fazla bilgi [için, ATL Kayıt Defteri Bileşeni (Registrar)](../../atl/atl-registry-component-registrar.md)makalesine bakın.

## <a name="declare_registry_resourceid"></a><a name="declare_registry_resourceid"></a>DECLARE_REGISTRY_RESOURCEID

[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource) ile aynı, bir dize adı yerine kaynağı tanımlamak için sihirbaz tarafından oluşturulan uINT kullanması dışında.

```
DECLARE_REGISTRY_RESOURCEID( x )
```

### <a name="parameters"></a>Parametreler

*X*<br/>
[içinde] Kaynağınızın sihirbaz tarafından oluşturulan tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

ATL Project Sihirbazı'nı kullanarak bir nesne veya denetim oluşturduğunuzda, sihirbaz komut dosyası tabanlı kayıt defteri desteğini otomatik olarak uygular ve dosyalarınıza DECLARE_REGISTRY_RESOURCEID makroekler.

En iyi duruma getirilmiş kayıt defteri erişimi için ATL Kayıt Defteri Bileşeni (Registrar) ile statik olarak bağlantı kurabilirsiniz. Kayıt Şirketi koduna statik olarak bağlanmak için, *stdafx.h* dosyanıza (Visual Studio 2019 ve sonrası*için pch.h)* aşağıdaki satırı ekleyin:

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

ATL'nin çalışma zamanında değiştirme değerlerini değiştirmesini istiyorsanız, DECLARE_REGISTRY_RESOURCE veya DECLARE_REGISTRY_RESOURCEID makrosu belirtmeyin. Bunun yerine, her `_ATL_REGMAP_ENTRIES` girişin çalışma zamanında yer tutucuyu değiştirmek için bir değerle eşleştirilmiş değişken bir yer tutucu içerdiği bir dizi yapı oluşturun. Sonra [CAtlModule arayın::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) veya [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), dizi geçen. Bu, `_ATL_REGMAP_ENTRIES` yapılardaki tüm değiştirme değerlerini Kayıt Defteri'nin değiştirme haritasına ekler.

Değiştirilebilir parametreler ve komut dosyası hakkında daha fazla bilgi [için, ATL Kayıt Defteri Bileşeni (Registrar)](../../atl/atl-registry-component-registrar.md)makalesine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Makrolar](../../atl/reference/atl-macros.md)
