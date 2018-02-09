---
title: "CPrivateObjectSecurityDesc sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::ConvertToAutoInherit
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Create
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Get
- ATLSECURITY/ATL::CPrivateObjectSecurityDesc::Set
dev_langs:
- C++
helpviewer_keywords:
- CPrivateObjectSecurityDesc class
ms.assetid: 2c4bbb13-bf99-4833-912a-197f6815bb5d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4845d652d2b1dceb8ffc0f2772f88565eb81e29
ms.sourcegitcommit: a5916b48541f804a79891ff04e246628b5f9a24a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/09/2018
---
# <a name="cprivateobjectsecuritydesc-class"></a>CPrivateObjectSecurityDesc sınıfı
Bu sınıf, bir özel nesneye güvenli tanımlayıcısı nesnesi temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CPrivateObjectSecurityDesc : public CSecurityDesc
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc](#cprivateobjectsecuritydesc)|Oluşturucu.|  
|[CPrivateObjectSecurityDesc::~CPrivateObjectSecurityDesc](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CPrivateObjectSecurityDesc::ConvertToAutoInherit](#converttoautoinherit)|Güvenlik tanımlayıcısı ve onun erişim denetim listelerini (ACL'ler) otomatik yayma devralınabilir erişim denetimi girişlerinin (ACE'ler) destekleyen bir biçime dönüştürmek için bu yöntemi çağırın.|  
|[CPrivateObjectSecurityDesc::Create](#create)|Ayırmak ve arama kaynak yöneticisi tarafından oluşturulan özel nesne kendine bağlı güvenlik tanımlayıcısı başlatmak için bu yöntemi çağırın.|  
|[CPrivateObjectSecurityDesc::Get](#get)|Özel bir nesnenin güvenlik tanımlayıcısından bilgilerini almak için bu yöntemi çağırın.|  
|[CPrivateObjectSecurityDesc::Set](#set)|Özel bir nesnenin güvenlik tanımlayıcısı değiştirmek için bu yöntemi çağırın.|  
  
### <a name="operators"></a>İşleçler  
  
|||  
|-|-|  
|[işleç =](#operator_eq)|Atama işleci.|  
  
## <a name="remarks"></a>Açıklamalar  
 Bu sınıf türetilen [CSecurityDesc](../../atl/reference/csecuritydesc-class.md), oluşturma ve özel bir nesnenin güvenlik tanımlayıcısı yönetme için yöntemleri sağlar.  
  
 Erişim denetimi modeli Windows giriş için bkz: [erişim denetimi](http://msdn.microsoft.com/library/windows/desktop/aa374860) Windows SDK'sındaki.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 [CSecurityDesc](../../atl/reference/csecuritydesc-class.md)  
  
 `CPrivateObjectSecurityDesc`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsecurity.h  
  
##  <a name="converttoautoinherit"></a>  CPrivateObjectSecurityDesc::ConvertToAutoInherit  
 Güvenlik tanımlayıcısı ve onun erişim denetim listelerini (ACL'ler) otomatik yayma devralınabilir erişim denetimi girişlerinin (ACE'ler) destekleyen bir biçime dönüştürmek için bu yöntemi çağırın.  
  
```
bool ConvertToAutoInherit(  
    const CSecurityDesc* pParent,
    GUID* ObjectType,
    bool bIsDirectoryObject,
    PGENERIC_MAPPING GenericMapping) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pParent`  
 İşaretçi bir [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) nesnenin üst kapsayıcıya başvuran nesne. Üst kapsayıcı ise, bu parametre NULL olur.  
  
 `ObjectType`  
 İşaretçi bir **GUID** geçerli nesneyle ilişkili nesne türünü tanımlayan yapısı. Ayarlama `ObjectType` nesne bir GUID yoksa null.  
  
 `bIsDirectoryObject`  
 Yeni nesne diğer nesnelerin içerip içeremeyeceğini belirtir. Doğru değeri, yeni bir nesne bir kapsayıcı gösterir. False değeri, yeni nesnenin bir kapsayıcı olmadığını gösterir.  
  
 `GenericMapping`  
 İşaretçi bir [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) genel her nesne için belirli haklar sağdan eşlemesi yapısı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu isteğe bağlı erişim denetimi ACE'ler (DACL) listesinde olup olmadığını belirlemek için yöntemi girişimleri ve sistem erişim denetimi listesi (SACL) geçerli güvenlik tanımlayıcısı üst güvenlik tanımlayıcısından devralındığını. Çağırır [ConvertToAutoInheritPrivateObjectSecurity](http://msdn.microsoft.com/library/windows/desktop/aa376403) işlevi.  
  
##  <a name="cprivateobjectsecuritydesc"></a>  CPrivateObjectSecurityDesc::CPrivateObjectSecurityDesc  
 Oluşturucu.  
  
```
CPrivateObjectSecurityDesc() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Başlatır `CPrivateObjectSecurityDesc` nesnesi.  
  
##  <a name="dtor"></a>  CPrivateObjectSecurityDesc::~CPrivateObjectSecurityDesc  
 Yok Edicisi.  
  
```
~CPrivateObjectSecurityDesc() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yok Edicisi ayrılan tüm kaynakları serbest bırakır ve özel nesnenin güvenlik tanımlayıcısı siler.  
  
##  <a name="create"></a>  CPrivateObjectSecurityDesc::Create  
 Ayırmak ve arama kaynak yöneticisi tarafından oluşturulan özel nesne kendine bağlı güvenlik tanımlayıcısı başlatmak için bu yöntemi çağırın.  
  
```
bool Create(  
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    bool bIsDirectoryObject,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();

bool Create(  
    const CSecurityDesc* pParent,
    const CSecurityDesc* pCreator,
    GUID* ObjectType,
    bool bIsContainerObject,
    ULONG AutoInheritFlags,
    const CAccessToken& Token,
    PGENERIC_MAPPING GenericMapping) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `pParent`  
 İşaretçi bir [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) içinde yeni bir nesne oluşturulmakta üst dizini başvuran nesne. Üst dizini yok ise NULL olarak ayarlayın.  
  
 `pCreator`  
 Nesne oluşturucusu tarafından sağlanan bir güvenlik açıklayıcısı işaretçi. Nesnenin oluşturucusu yeni nesne için güvenlik bilgilerini açıkça geçemezse, bu parametre NULL olarak ayarlayın.  
  
 `bIsDirectoryObject`  
 Yeni nesne diğer nesnelerin içerip içeremeyeceğini belirtir. Doğru değeri, yeni bir nesne bir kapsayıcı gösterir. False değeri, yeni nesnenin bir kapsayıcı olmadığını gösterir.  
  
 `Token`  
 Başvuru [CAccessToken](../../atl/reference/caccesstoken-class.md) nesne adına nesne oluşturuluyor istemci işlemi için.  
  
 `GenericMapping`  
 İşaretçi bir [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) genel her nesne için belirli haklar sağdan eşlemesi yapısı.  
  
 `ObjectType`  
 İşaretçi bir **GUID** geçerli nesneyle ilişkili nesne türünü tanımlayan yapısı. Ayarlama `ObjectType` nesne bir GUID yoksa null.  
  
 *bIsContainerObject*  
 Yeni nesne diğer nesnelerin içerip içeremeyeceğini belirtir. Doğru değeri, yeni bir nesne bir kapsayıcı gösterir. False değeri, yeni nesnenin bir kapsayıcı olmadığını gösterir.  
  
 `AutoInheritFlags`  
 Erişim denetimi girişlerinin (ACE'ler) öğesinden devralınan nasıl kontrol bit bayrakları kümesi `pParent`. Bkz: [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581) daha fazla ayrıntı için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntemi çağırır [CreatePrivateObjectSercurity](http://msdn.microsoft.com/library/windows/desktop/aa376405) veya [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581).  
  
 İkinci yöntem, yeni nesnenin nesne türü GUID belirterek veya ACE'ler nasıl devralınan denetleme verir.  
  
> [!NOTE]
>  Bitişik bir bellek bloğu tüm güvenlik bilgilerini depolayan bir güvenlik tanımlayıcısı kendine bağlı güvenlik tanımlayıcısıdır.  
  
##  <a name="get"></a>  CPrivateObjectSecurityDesc::Get  
 Özel bir nesnenin güvenlik tanımlayıcısından bilgilerini almak için bu yöntemi çağırın.  
  
```
bool Get(  
    SECURITY_INFORMATION si,
    CSecurityDesc* pResult) const throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `si`  
 Almak için güvenlik tanımlayıcısı bölümlerini gösteren bir bit bayrakları kümesi. Bu değer bir bileşimi olabilir [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) bit bayrakları.  
  
 `pResult`  
 İşaretçi bir [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) belirtilen güvenlik tanımlayıcısından istenen bilgilerin bir kopyasını alan nesnesi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 Güvenlik tanımlayıcısı yapısı ve bir güvenliği sağlanabilir nesne için güvenlik bilgilerini içeren ilişkili veri ' dir.  
  
##  <a name="operator_eq"></a>  CPrivateObjectSecurityDesc::operator =  
 Atama işleci.  
  
```
CPrivateObjectSecurityDesc& operator= (const CPrivateObjectSecurityDesc& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rhs`  
 `CPrivateObjectSecurityDesc` Nesne geçerli nesneye atamak için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş döndürür `CPrivateObjectSecurityDesc` nesnesi.  
  
##  <a name="set"></a>  CPrivateObjectSecurityDesc::Set  
 Özel bir nesnenin güvenlik tanımlayıcısı değiştirmek için bu yöntemi çağırın.  
  
```
bool Set(  
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();

bool Set(  
    SECURITY_INFORMATION si,
    const CSecurityDesc& Modification,
    ULONG AutoInheritFlags,
    PGENERIC_MAPPING GenericMapping,
    const CAccessToken& Token) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `si`  
 Ayarlamak için güvenlik tanımlayıcısı bölümlerini gösteren bir bit bayrakları kümesi. Bu değer bir bileşimi olabilir [SECURITY_INFORMATION](http://msdn.microsoft.com/library/windows/desktop/aa379573) bit bayrakları.  
  
 *Değiştirme*  
 İşaretçi bir [CSecurityDesc](../../atl/reference/csecuritydesc-class.md) nesnesi. Bu güvenlik tanımlayıcısı bölümlerini belirtilen tarafından `si` parametresi, nesnenin güvenlik tanımlayıcısı için uygulanır.  
  
 `GenericMapping`  
 İşaretçi bir [GENERIC_MAPPING](http://msdn.microsoft.com/library/windows/desktop/aa446633) genel her nesne için belirli haklar sağdan eşlemesi yapısı.  
  
 `Token`  
 Başvuru [CAccessToken](../../atl/reference/caccesstoken-class.md) nesne adına nesne oluşturuluyor istemci işlemi için.  
  
 `AutoInheritFlags`  
 Erişim denetimi girişlerinin (ACE'ler) öğesinden devralınan nasıl kontrol bit bayrakları kümesi `pParent`. Bkz: [CreatePrivateObjectSecurityEx](http://msdn.microsoft.com/library/windows/desktop/aa446581) daha fazla ayrıntı için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Başarılı olma durumunda true, aksi durumda false değerini döndürür.  
  
### <a name="remarks"></a>Açıklamalar  
 İkinci yöntem, nesnenin nesne türü GUID belirterek veya ACE'ler nasıl devralınan denetleme verir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Güvenlik genel işlevler](../../atl/reference/security-global-functions.md)   
 [CSecurityDesc Sınıfı](../../atl/reference/csecuritydesc-class.md)
