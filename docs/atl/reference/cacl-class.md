---
title: "CAcl sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAcl
- ATLSECURITY/ATL::CAcl
- ATLSECURITY/ATL::CAcl::CAccessMaskArray
- ATLSECURITY/ATL::CAcl::CAceFlagArray
- ATLSECURITY/ATL::CAcl::CAceTypeArray
- ATLSECURITY/ATL::CAcl::CAcl
- ATLSECURITY/ATL::CAcl::GetAceCount
- ATLSECURITY/ATL::CAcl::GetAclEntries
- ATLSECURITY/ATL::CAcl::GetAclEntry
- ATLSECURITY/ATL::CAcl::GetLength
- ATLSECURITY/ATL::CAcl::GetPACL
- ATLSECURITY/ATL::CAcl::IsEmpty
- ATLSECURITY/ATL::CAcl::IsNull
- ATLSECURITY/ATL::CAcl::RemoveAce
- ATLSECURITY/ATL::CAcl::RemoveAces
- ATLSECURITY/ATL::CAcl::SetEmpty
- ATLSECURITY/ATL::CAcl::SetNull
dev_langs: C++
helpviewer_keywords: CAcl class
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cd3b17c3cf74e87b709353a8dd2cd00c5355c7fc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="cacl-class"></a>CAcl sınıfı
Bu sınıf için sarmalayıcı, bir `ACL` (erişim denetim listesi) yapısı.  
  
> [!IMPORTANT]
>  Bu sınıf ve üyelerini Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class CAcl
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-typedefs"></a>Genel tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAcl::CAccessMaskArray](#caccessmaskarray)|Bir dizi `ACCESS_MASK`s.|  
|[CAcl::CAceFlagArray](#caceflagarray)|Bir dizi `BYTE`s.|  
|[CAcl::CAceTypeArray](#cacetypearray)|Bir dizi `BYTE`s.|  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAcl::CAcl](#cacl)|Oluşturucu.|  
|[CAcl:: ~ CAcl](#dtor)|Yok Edicisi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAcl::GetAceCount](#getacecount)|Erişim denetim girdisi (ACE) nesneleri döndürür.|  
|[CAcl::GetAclEntries](#getaclentries)|Erişim denetimi listesi (ACL) girişleri alır `CAcl` nesnesi.|  
|[CAcl::GetAclEntry](#getaclentry)|Tüm bir girişe hakkındaki bilgileri alır bir `CAcl` nesnesi.|  
|[CAcl::GetLength](#getlength)|ACL uzunluğunu döndürür.|  
|[CAcl::GetPACL](#getpacl)|PACL (bir ACL işaretçisi) döndürür.|  
|[CAcl::IsEmpty](#isempty)|Testleri `CAcl` girişleri için nesnesi.|  
|[CAcl::IsNull](#isnull)|Durumunu döndüren `CAcl` nesnesi.|  
|[CAcl::RemoveAce](#removeace)|Belirli bir ACE (erişim denetim girdisi) kaldırır `CAcl` nesnesi.|  
|[CAcl::RemoveAces](#removeaces)|Tüm ACE'ler (erişim denetimi girdileri) kaldırır `CAcl` , uygulamak için verilen `CSid`.|  
|[CAcl::SetEmpty](#setempty)|İşaretleri `CAcl` nesnesi boş.|  
|[CAcl::SetNull](#setnull)|İşaretleri `CAcl` olarak nesne `NULL`.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CAcl::operator const ACL *](#operator_const_acl__star)|Atamalar bir `CAcl` nesnesine bir `ACL` yapısı.|  
|[CAcl::operator =](#operator_eq)|Atama işleci.|  
  
## <a name="remarks"></a>Açıklamalar  
 **ACL** bir ACL (erişim denetim listesi) üstbilgisinin yapısıdır. Bir ACL sıfır veya daha fazla sıralı bir listesini içeren [ACE'ler](http://msdn.microsoft.com/library/windows/desktop/aa374868) (erişim denetimi girdileri). ACL içindeki tek tek ACE'ler 0'dan numaralandırılır *n-1*, burada  *n*  ACL ACE'ler sayısıdır. Bir ACL düzenlerken, bir uygulama içinde ACL erişim denetim girdisi (ACE) tarafından dizinini ifade eder.  
  
 İki ACL türleri şunlardır:  
  
-   İsteğe bağlı  
  
-   Sistem  
  
 Herkes verilen ya da gizli ACL nesnenin sahibi tarafından denetlenen **WRITE_DAC** nesneye erişim. Bu nesneye erişim belirli kullanıcılar ve gruplar sahip belirtir. Örneğin, bir dosyanın sahibi bir gizli ACL hangi kullanıcıların ve grupların olabilir ve dosyaya erişim olamaz denetlemek için kullanabilirsiniz.  
  
 Bir nesne, bir sistem bir sistem yöneticisi tarafından denetlenen ACL biçiminde ilişkili sistem düzeyinde güvenlik bilgileri de sağlayabilirsiniz. Sistem ACL, bir nesneye erişim girişimlerini denetlemek için sistem yöneticisine izin verebilirsiniz.  
  
 Daha fazla ayrıntı için bkz: [ACL](http://msdn.microsoft.com/library/windows/desktop/aa374872) Windows SDK'sındaki tartışma.  
  
 Erişim denetimi modeli Windows giriş için bkz: [erişim denetimi](http://msdn.microsoft.com/library/windows/desktop/aa374860) Windows SDK'sındaki.  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** atlsecurity.h  
  
##  <a name="caccessmaskarray"></a>CAcl::CAccessMaskArray  
 ACCESS_MASK nesnelerinin bir dizisi.  
  
```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu typedef kullanılan erişim hakları erişim denetimi girişlerinin (ACE'ler) depolamak için kullanılan dizi türünü belirtir.  
  
##  <a name="caceflagarray"></a>CAcl::CAceFlagArray  
 Bir bayt dizisi.  
  
```
typedef CAtlArray<BYTE> CAceFlagArray;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu typedef erişim denetim girdisi (ACE) türüne özgü denetim bayrakları tanımlamak için kullanılan dizi türünü belirtir. Bkz: [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) olası bayraklar tam listesi için tanımı.  
  
##  <a name="cacetypearray"></a>CAcl::CAceTypeArray  
 Bir bayt dizisi.  
  
```
typedef CAtlArray<BYTE> CAceTypeArray;
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu typedef ACCESS_ALLOWED_ACE_TYPE veya ACCESS_DENIED_ACE_TYPE gibi erişim denetim girdisi (ACE) nesneleri yapısını tanımlamak için kullanılan dizi türünü belirtir. Bkz: [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) olası türlerinin tam listesi için tanımını.  
  
##  <a name="cacl"></a>CAcl::CAcl  
 Oluşturucu.  
  
```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rhs`  
 Varolan bir `CAcl` nesnesi.  
  
### <a name="remarks"></a>Açıklamalar  
 `CAcl` Nesne isteğe bağlı olarak var olan kullanılarak oluşturulabilir `CAcl` nesnesi.  
  
##  <a name="dtor"></a>CAcl:: ~ CAcl  
 Yok Edicisi.  
  
```
virtual ~CAcl() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yok Edicisi nesne tarafından alınan tüm kaynakları serbest bırakır.  
  
##  <a name="getacecount"></a>CAcl::GetAceCount  
 Erişim denetim girdisi (ACE) nesneleri döndürür.  
  
```
virtual UINT GetAceCount() const throw() = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 ACE girişlerinde sayısını döndürür `CAcl` nesnesi.  
  
##  <a name="getaclentries"></a>CAcl::GetAclEntries  
 Erişim denetimi listesi (ACL) girişleri alır `CAcl` nesnesi.  
  
```
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `pSids`  
 Bir dizi için bir işaretçi [CSID](../../atl/reference/csid-class.md) nesneleri.  
  
 *pAccessMasks*  
 Erişim maskesi.  
  
 *pAceTypes*  
 Erişim denetimi girişinin ( **ACE**) türleri.  
  
 *pAceFlags*  
 **ACE** bayrakları.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem ayrıntılarını dizi parametrelerle doldurur her **ACE** içinde yer alan nesne `CAcl` nesne. Ayrıntılar için belirli bir dizi gerekli olmadığında NULL kullanın.  
  
 Her bir dizinin içeriğini birbirlerine, diğer bir deyişle, ilk öğesi karşılık gelen `CAccessMaskArray` dizi karşılık gelen ilk öğe için `CSidArray` dizi ve benzeri.  
  
 Bkz: [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) ACE türleri ve bayrakları hakkında daha fazla ayrıntı için.  
  
##  <a name="getaclentry"></a>CAcl::GetAclEntry  
 Tüm erişim denetimi listesi (ACL) bir giriş bilgilerini alır.  
  
```
void GetAclEntry(
    UINT nIndex,
    CSid* pSid,
    ACCESS_MASK* pMask = NULL,
    BYTE* pType = NULL,
    BYTE* pFlags = NULL,
    GUID* pObjectType = NULL,
    GUID* pInheritedObjectType = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Almak için ACL giriş dizini.  
  
 `pSid`  
 [CSID](../../atl/reference/csid-class.md) nesne ACL giriş uygulandığı.  
  
 *pMask*  
 Erişim vermek veya reddetmek için izinleri belirterek maskesi.  
  
 `pType`  
 ACE türü.  
  
 `pFlags`  
 ACE bayraklar.  
  
 `pObjectType`  
 Nesne türü. Bu GUID_NULL için nesne türü ACE belirtilmezse veya AS nesne ACE değilse ayarlanır.  
  
 `pInheritedObjectType`  
 Devralınan nesne türü. Bu GUID_NULL için devralınan nesne türü ACE belirtilmezse veya AS nesne ACE değilse ayarlanır.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem tüm bilgileri hakkında daha fazla bilgi sağlayan bir tek tek ACE alacak [CAcl::GetAclEntries](#getaclentries) tek başına kullanılabilir hale getirir.  
  
 Bkz: [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) ACE türleri ve bayrakları hakkında daha fazla ayrıntı için.  
  
##  <a name="getlength"></a>CAcl::GetLength  
 Erişim denetimi listesi (ACL) uzunluğunu döndürür.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Gerekli uzunluğa bayt cinsinden tutmak gerekli döndürür **ACL** yapısı.  
  
##  <a name="getpacl"></a>CAcl::GetPACL  
 Bir işaretçi bir erişim denetimi listesi (ACL) döndürür.  
  
```
const ACL* GetPACL() const throw(...);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir işaretçi döndürür **ACL** yapısı.  
  
##  <a name="isempty"></a>CAcl::IsEmpty  
 Testleri `CAcl` girişleri için nesnesi.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 Döndürür **true** varsa `CAcl` nesnesi NULL değil ve hiçbir giriş içerir. Döndürür **false** varsa `CAcl` nesne ya da null ya da en az bir giriş içerir.  
  
##  <a name="isnull"></a>CAcl::IsNull  
 Durumunu döndüren `CAcl` nesnesi.  
  
```
bool IsNull() const throw();
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Döndürür **true** varsa `CAcl` nesnesi, NULL, **false** Aksi takdirde.  
  
##  <a name="operator_const_acl__star"></a>CAcl::operator const ACL *  
 Atamalar bir `CAcl` nesnesine bir **ACL** (erişim denetim listesi) yapısı.  
  
```  
operator const ACL *() const throw(...);
```  
  
### <a name="remarks"></a>Açıklamalar  
 Adresini döndürür **ACL** yapısı.  
  
##  <a name="operator_eq"></a>CAcl::operator =  
 Atama işleci.  
  
```
CAcl& operator= (const CAcl& rhs) throw(...);
```  
  
### <a name="parameters"></a>Parametreler  
 `rhs`  
 `CAcl` Varolan nesnesine atanamadı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Güncelleştirilmiş bir başvuru döndürür `CAcl` nesnesi.  
  
##  <a name="removeace"></a>CAcl::RemoveAce  
 Belirli bir ACE (erişim denetim girdisi) kaldırır **CAcl** nesnesi.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>Parametreler  
 `nIndex`  
 Kaldırmak için ACE giriş dizini.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yöntem türetilir [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).  
  
##  <a name="removeaces"></a>CAcl::RemoveAces  
 Yanıtla ACE (erişim denetimi girdileri) kaldırır `CAcl` , uygulamak için verilen `CSid`.  
  
```
bool RemoveAces(const CSid& rSid) throw(...)
```  
  
### <a name="parameters"></a>Parametreler  
 `rSid`  
 Bir başvuru bir `CSid` nesnesi.  
  
##  <a name="setempty"></a>CAcl::SetEmpty  
 İşaretleri `CAcl` nesnesi boş.  
  
```
void SetEmpty() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `CAcl` Boş veya NULL ayarlayın: iki durumlu farklıdır.  
  
##  <a name="setnull"></a>CAcl::SetNull  
 İşaretleri `CAcl` nesnesi NULL olarak.  
  
```
void SetNull() throw();
```  
  
### <a name="remarks"></a>Açıklamalar  
 `CAcl` Boş veya NULL ayarlayın: iki durumlu farklıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../atl/atl-class-overview.md)   
 [Güvenlik Genel İşlevleri](../../atl/reference/security-global-functions.md)
