---
title: Kayıt defteri makroları
ms.date: 11/04/2016
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
ms.openlocfilehash: bced900cd7bac666daf415d91a4540828c769025
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660388"
---
# <a name="registry-macros"></a>Kayıt defteri makroları

Bu makrolar, kullanışlı bir tür kitaplığı ve kayıt defteri özellikleri tanımlar.

|||
|-|-|
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|ATL bağımlılığı önlemek için nesne olması nesneniz için kayıt kodu istediğiniz gösterir DLL.|
|[DECLARE_LIBID](#declare_libid)|ATL almak bir yol sağlar *libid* tür kitaplığının.|
|[DECLARE_NO_REGISTRY](#declare_no_registry)|Varsayılan ATL kayıt önler.|
|[DECLARE_REGISTRY](#declare_registry)|Girer veya giriş ana nesnenin sistem kayıt defterinde kaldırır.|
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|Otomatik olarak kaydetmek için gereken bilgileri belirtir *AppID*.|
|[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)|Adlandırılmış kaynağı bulur ve içindeki kayıt betiği çalıştırır.|
|[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)|Bir kimlik numarası tarafından tanımlanan kaynağa bulur ve içindeki kayıt betiği çalıştırır.|

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlcom.h

##  <a name="_atl_static_registry"></a>  _ATL_STATIC_REGISTRY

ATL bağımlılığı önlemek için nesne olması nesneniz için kayıt kodu istediğiniz gösteren bir simge DLL.

```
#define _ATL_STATIC_REGISTRY
```

### <a name="remarks"></a>Açıklamalar

ATL_STATIC_REGISTRY tanımlarken, aşağıdaki kodu kullanmanız gerekir:

[!code-cpp[NVC_ATL_EventHandlingSample#5](../../atl/codesnippet/cpp/registry-macros_1.cpp)]

##  <a name="declare_libid"></a>  DECLARE_LIBID

ATL almak bir yol sağlar *libid* tür kitaplığının.

```
DECLARE_LIBID( libid )
```

### <a name="parameters"></a>Parametreler

*Kitaplık kimliği*<br/>
Tür kitaplığının GUID.

### <a name="remarks"></a>Açıklamalar

İçinde DECLARE_LIBID kullanmak bir `CAtlModuleT`-türetilmiş sınıf.

### <a name="example"></a>Örnek

Sihirbazın ürettiği ATL projeleri olmayan öznitelikli Bu makroyu kullanarak, bir örnek olacaktır.

##  <a name="declare_no_registry"></a>  DECLARE_NO_REGISTRY

Bu makro göründüğü sınıf için herhangi bir varsayılan ATL kayıt kaçınmak istiyorsanız DECLARE_NO_REGISTRY kullanın.

```
DECLARE_NO_REGISTRY()
```

##  <a name="declare_registry"></a>  DECLARE_REGISTRY

Sistem kayıt defterine standart sınıf kayıt girer veya sistem kayıt defterinden kaldırır.

```
DECLARE_REGISTRY(
    class,
    pid,
    vpid,
    nid,
    flags )
```

### <a name="parameters"></a>Parametreler

*class*<br/>
[in] Geriye dönük uyumluluk için dahildir.

*PID*<br/>
[in] Sürüme özgü program tanımlayıcısı bir LPCTSTR.

*vpid*<br/>
[in] Bir sürüm bağımsız program tanımlayıcısı bir LPCTSTR.

*nid*<br/>
[in] Kayıt programı'nın açıklaması kullanmak için kaynak dizenin bir dizin UINT.

*bayrakları*<br/>
[in] Kayıt defterinde programın iş parçacığı modeli içeren bir DWORD. Aşağıdaki değerlerden biri olmalıdır: THREADFLAGS_APARTMENT, THREADFLAGS_BOTH veya AUTPRXFLAG.

### <a name="remarks"></a>Açıklamalar

Standart kayıt CLSID, program kimliği, sürüm bağımsız program kimliği, açıklama dizesi ve iş parçacığı modeli oluşur.

Bir nesne oluşturun veya ATL ekleme sınıfı Sihirbazı'nı kullanarak denetimi, sihirbaz otomatik olarak betik tabanlı kayıt defteri destek uygular ve ekler [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) dosyalarınıza makrosu. Betik tabanlı kayıt defteri destek istemiyorsanız, bu makroyu DECLARE_REGISTRY ile değiştirmeniz gerekiyor. DECLARE_REGISTRY yalnızca kayıt defterine yukarıda beş temel anahtar ekler. El ile kayıt defterine diğer anahtarlar eklemek için kod yazmanız gerekir.

##  <a name="declare_registry_appid_resourceid"></a>  DECLARE_REGISTRY_APPID_RESOURCEID

Otomatik olarak kaydetmek için gereken bilgileri belirtir *AppID*.

```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid,
    appid )
```

### <a name="parameters"></a>Parametreler

*resid*<br/>
Kaynak Kimliği hakkında bilgi içeren .rgs dosyanın *AppID*.

*Uygulama Kimliği*<br/>
BİR GUID.

### <a name="remarks"></a>Açıklamalar

İçinde DECLARE_REGISTRY_APPID_RESOURCEID kullanmak bir `CAtlModuleT`-türetilmiş sınıf.

### <a name="example"></a>Örnek

Sınıf Ekle kod Sihirbazı ile ATL projelere eklenen sınıfları bu makroyu kullanarak, bir örnek olacaktır.

##  <a name="declare_registry_resource"></a>  DECLARE_REGISTRY_RESOURCE

Kayıt defteri dosyasını içeren bir adlandırılmış kaynağı alır ve nesneler sistem kayıt defterine girin ya da sistem kayıt defterinden kaldırmak için betiği çalıştırır.

```
DECLARE_REGISTRY_RESOURCE( x )
```

### <a name="parameters"></a>Parametreler

*x*<br/>
[in] Kaynağınızın tanımlayıcı dize.

### <a name="remarks"></a>Açıklamalar

Bir nesne oluşturun veya ATL projesi Sihirbazı'nı kullanarak denetlemek, sihirbaz otomatik olarak betik tabanlı kayıt defteri destek uygulamak ve ekleme [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) DECLARE_REGISTRY_ için benzer makrosu Dosyalarınıza kaynak.

Statik olarak en iyi duruma getirilmiş kayıt defteri erişimi için ATL kayıt defteri bileşeni (Kaydedici) ile bağlayabilirsiniz. Kaydedici koduna statik olarak bağlamak için stdafx.h dosyanızın aşağıdaki satırı ekleyin:

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

ATL çalışma zamanında değiştirme değerlerini değiştirmek isterseniz, DECLARE_REGISTRY_RESOURCE veya DECLARE_REGISTRY_RESOURCEID makrosu belirtmeyin. Bunun yerine, bir dizi oluşturma `_ATL_REGMAP_ENTRIES` yapıları, burada her giriş içeren bir değişken yer tutucu eşleştirilmiş bir değerle çalışma zamanında yer tutucusunu değiştirin. Ardından çağırın [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) veya [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), dizisi geçirerek. Bu tüm yeni değerler ekler `_ATL_REGMAP_ENTRIES` yapılarını şirketinin değiştirme eşlemesi.

Değiştirilebilir parametreler ve betik oluşturma hakkında daha fazla bilgi için bkz [ATL kayıt defteri bileşeni (Kaydedici)](../../atl/atl-registry-component-registrar.md).

##  <a name="declare_registry_resourceid"></a>  DECLARE_REGISTRY_RESOURCEID

Aynı [DECLARE_REGISTRY_RESOURCE](#declare_registry_resource) bir dize adı yerine kaynağı tanımlamak için bir sihirbaz tarafından oluşturulan UINT kullanması hariç, aynıdır.

```
DECLARE_REGISTRY_RESOURCEID( x )
```

### <a name="parameters"></a>Parametreler

*x*<br/>
[in] Sihirbazın ürettiği kaynak tanımlayıcısı.

### <a name="remarks"></a>Açıklamalar

Bir nesne veya ATL projesi Sihirbazı'nı kullanarak denetim oluşturduğunuzda, sihirbaz otomatik olarak betik tabanlı kayıt defteri destek uygulamak ve DECLARE_REGISTRY_RESOURCEID makrosu dosyalarınıza ekleyin.

Statik olarak en iyi duruma getirilmiş kayıt defteri erişimi için ATL kayıt defteri bileşeni (Kaydedici) ile bağlayabilirsiniz. Kaydedici koduna statik olarak bağlamak için stdafx.h dosyanızın aşağıdaki satırı ekleyin:

[!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]

ATL çalışma zamanında değiştirme değerlerini değiştirmek isterseniz, DECLARE_REGISTRY_RESOURCE veya DECLARE_REGISTRY_RESOURCEID makrosu belirtmeyin. Bunun yerine, bir dizi oluşturma `_ATL_REGMAP_ENTRIES` yapıları, burada her giriş içeren bir değişken yer tutucu eşleştirilmiş bir değerle çalışma zamanında yer tutucusunu değiştirin. Ardından çağırın [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) veya [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), dizisi geçirerek. Bu tüm yeni değerler ekler `_ATL_REGMAP_ENTRIES` yapılarını şirketinin değiştirme eşlemesi.

Değiştirilebilir parametreler ve betik oluşturma hakkında daha fazla bilgi için bkz [ATL kayıt defteri bileşeni (Kaydedici)](../../atl/atl-registry-component-registrar.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Makroları](../../atl/reference/atl-macros.md)
