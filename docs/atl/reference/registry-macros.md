---
title: Kayıt defteri makroları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::_ATL_STATIC_REGISTRY
- atlcom/ATL::DECLARE_LIBID
- atlcom/ATL::DECLARE_NO_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY_APPID_RESOURCEID
- atlcom/ATL::DECLARE_REGISTRY_RESOURCE
- atlcom/ATL::DECLARE_REGISTRY_RESOURCEID
dev_langs:
- C++
helpviewer_keywords:
- registry, ATL macros
ms.assetid: 3ee041da-c63b-42a4-89cf-2a4b2a6f81ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed9b172217f1ca7ada7d8752151126b53055df37
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32365223"
---
# <a name="registry-macros"></a>Kayıt defteri makroları
Bu makroları yararlı türü kitaplığı ve kayıt defteri özellikleri tanımlayın.  
  
|||  
|-|-|  
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|ATL bir bağımlılığı önlemek için nesnesindeki olmasını nesnenizin kayıt kodunu istediğiniz gösterir DLL.|  
|[DECLARE_LIBID](#declare_libid)|ATL elde etmek bir yoldur *kitaplık kimliği* tür kitaplığı.|  
|[DECLARE_NO_REGISTRY](#declare_no_registry)|Varsayılan ATL kayıt önler.|  
|[DECLARE_REGISTRY](#declare_registry)|Girer veya sistem kayıt defterinde ana nesnenin giriş kaldırır.|  
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|Otomatik olarak kaydetmek için gereken bilgileri belirtir *AppID*.|  
|[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)|Adlandırılmış kaynak bulur ve içindeki kayıt defteri komut dosyasını çalıştırır.|  
|[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)|Bir kimlik numarası tarafından tanımlanan kaynağa bulur ve içindeki kayıt defteri komut dosyasını çalıştırır.|  

## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlcom.h  
  
    
##  <a name="_atl_static_registry"></a>  _ATL_STATIC_REGISTRY  
 ATL bir bağımlılığı önlemek için nesnesindeki olmasını nesnenizin kayıt kodunu istediğiniz gösteren bir simge DLL.  
  
```
#define _ATL_STATIC_REGISTRY
```  
  
### <a name="remarks"></a>Açıklamalar  
 Tanımladığınızda **ATL_STATIC_REGISTRY**, aşağıdaki kodu kullanmanız gerekir:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#5](../../atl/codesnippet/cpp/registry-macros_1.cpp)]  
  
##  <a name="declare_libid"></a>  DECLARE_LIBID  
 ATL elde etmek bir yoldur *kitaplık kimliği* tür kitaplığı.  
  
```
DECLARE_LIBID( libid )
```  
  
### <a name="parameters"></a>Parametreler  
 *Kitaplık kimliği*  
 Tür kitaplığı GUID.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `DECLARE_LIBID` içinde bir `CAtlModuleT`-türetilmiş sınıf.  
  
### <a name="example"></a>Örnek  
 Sihirbaz tarafından oluşturulan ATL projeleri olmayan öznitelikli bu makrosu kullanarak bir örnek olacaktır.  
  
##  <a name="declare_no_registry"></a>  DECLARE_NO_REGISTRY  
 Kullanım `DECLARE_NO_REGISTRY` bu makrosu göründüğü sınıfı için herhangi bir varsayılan ATL kayıt önlemek istiyorsanız.  
  
```
DECLARE_NO_REGISTRY()
```  
  
##  <a name="declare_registry"></a>  DECLARE_REGISTRY  
 Sistem kayıt defterine standart sınıf kaydı girer veya sistem kayıt defterinden kaldırır.  
  
```
DECLARE_REGISTRY(
    class, 
    pid, 
    vpid, 
    nid, 
    flags )
```  
  
### <a name="parameters"></a>Parametreler  
 `class`  
 [in] Geriye dönük uyumluluk için dahil.  
  
 `pid`  
 [in] Bir `LPCTSTR` olan bir sürüme özgü program tanımlayıcısı.  
  
 *vpid*  
 [in] Bir `LPCTSTR` diğer bir deyişle bir sürüm bağımsız program tanımlayıcısı.  
  
 *nid*  
 [in] A **UINT** diğer bir deyişle programının açıklaması kullanmak için kayıt defterinde kaynak dizesi dizini.  
  
 `flags`  
 [in] A `DWORD` program içeren kullanıcının iş parçacığı modeli kayıt defterinde. Aşağıdaki değerlerden biri olmalıdır: **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, veya **AUTPRXFLAG**.  
  
### <a name="remarks"></a>Açıklamalar  
 Standart kayıt CLSID, program kimliği, sürüm bağımsız program kimliği, açıklama dizesi ve iş parçacığı modeli oluşur.  
  
 Bir nesne oluşturduğunuzda ya da ATL ekleme sınıfı Sihirbazı'nı kullanarak denetimi Sihirbazı otomatik olarak betik tabanlı kayıt defteri destek uygular ve ekler [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) makrosu dosyalarınıza. Betik tabanlı kayıt defteri destek istemiyorsanız bu makrosu ile değiştirmeniz gerekiyor `DECLARE_REGISTRY`. `DECLARE_REGISTRY` yalnızca kayıt defterine yukarıda beş temel anahtarları ekler. El ile kayıt defterine diğer anahtarlar eklemek için kod yazmanız gerekir.  
  
##  <a name="declare_registry_appid_resourceid"></a>  DECLARE_REGISTRY_APPID_RESOURCEID  
 Otomatik olarak kaydetmek için gereken bilgileri belirtir *AppID*.  
  
```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid, 
    appid )
```  
  
### <a name="parameters"></a>Parametreler  
 *resid*  
 Kaynak Kimliği hakkında bilgi içeren .rgs dosyasının *AppID*.  
  
 *AppID*  
 BİR GUID.  
  
### <a name="remarks"></a>Açıklamalar  
 Kullanım `DECLARE_REGISTRY_APPID_RESOURCEID` içinde bir `CAtlModuleT`-türetilmiş sınıf.  
  
### <a name="example"></a>Örnek  
 ATL projeleri sınıfı Ekle kod Sihirbazı'nı kullanarak eklenen sınıflar bu makrosu kullanarak bir örnek olacaktır.  
  
##  <a name="declare_registry_resource"></a>  DECLARE_REGISTRY_RESOURCE  
 Kayıt defteri dosyasını içeren adlandırılmış kaynağı alır ve nesnelerin sistem kayıt defterine girin ya da sistem kayıt defterinden kaldırmak için komut dosyasını çalıştırır.  
  
```
DECLARE_REGISTRY_RESOURCE( x )
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Kaynağınız tanıtıcısı dize.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir nesne oluşturduğunuzda ya da ATL Proje Sihirbazı'nı kullanarak denetim sihirbaz otomatik olarak betik tabanlı kayıt defteri destek uygulamak ve ekleme [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) benzer makrosu `DECLARE_REGISTRY_RESOURCE`, dosyalar.  
  
 Statik olarak en iyi duruma getirilmiş kayıt defteri erişimi için ATL kayıt defteri bileşeni (Kaydedici) ile bağlayabilirsiniz. Kaydedici statik olarak bağlamak için stdafx.h dosyanızın aşağıdaki satırı ekleyin:  
  
 [!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 Çalışma zamanında değiştirme değeri yerine ATL istiyorsanız belirtmeyin `DECLARE_REGISTRY_RESOURCE` veya `DECLARE_REGISTRY_RESOURCEID` makrosu. Bunun yerine, bir dizi oluşturmak **_ATL_REGMAP_ENTRIES** , her giriş içerdiği değişken yer tutucu yapıları eşleştirilmiş yer tutucu çalışma zamanında değiştirmek için bir değere sahip. ' I çağırın [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) veya [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), dizi geçirme. Bu tüm değiştirme değerler ekler **_ATL_REGMAP_ENTRIES** kayıt şirketinin değiştirme eşlemesine yapıları.  

  
 Değiştirilebilir parametreler ve komut dosyası hakkında daha fazla bilgi için bkz: [ATL kayıt defteri bileşeni (Kaydedici)](../../atl/atl-registry-component-registrar.md).  
  
##  <a name="declare_registry_resourceid"></a>  DECLARE_REGISTRY_RESOURCEID  
 Aynı [DECLARE_REGISTRY_RESOURCE](#declare_registry_resource) sihirbaz tarafından oluşturulan kullanır ancak bu **UINT** bir dize adı yerine kaynak tanımlamak için.  
  
```
DECLARE_REGISTRY_RESOURCEID( x )
```  
  
### <a name="parameters"></a>Parametreler  
 *x*  
 [in] Sihirbaz tarafından oluşturulan kaynağınız tanıtıcısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bir nesne oluşturduğunuzda ya da ATL Proje Sihirbazı'nı kullanarak denetim sihirbaz otomatik olarak betik tabanlı kayıt defteri destek uygulamak ve ekleme `DECLARE_REGISTRY_RESOURCEID` makrosu dosyalarınıza.  
  
 Statik olarak en iyi duruma getirilmiş kayıt defteri erişimi için ATL kayıt defteri bileşeni (Kaydedici) ile bağlayabilirsiniz. Kaydedici statik olarak bağlamak için stdafx.h dosyanızın aşağıdaki satırı ekleyin:  
  
 [!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 Çalışma zamanında değiştirme değeri yerine ATL istiyorsanız belirtmeyin `DECLARE_REGISTRY_RESOURCE` veya `DECLARE_REGISTRY_RESOURCEID` makrosu. Bunun yerine, bir dizi oluşturmak **_ATL_REGMAP_ENTRIES** , her giriş içerdiği değişken yer tutucu yapıları eşleştirilmiş yer tutucu çalışma zamanında değiştirmek için bir değere sahip. ' I çağırın [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) veya [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), dizi geçirme. Bu tüm değiştirme değerler ekler **_ATL_REGMAP_ENTRIES** kayıt şirketinin değiştirme eşlemesine yapıları.  

  
 Değiştirilebilir parametreler ve komut dosyası hakkında daha fazla bilgi için bkz: [ATL kayıt defteri bileşeni (Kaydedici)](../../atl/atl-registry-component-registrar.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Makroları](../../atl/reference/atl-macros.md)
