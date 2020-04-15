---
title: CComGITPtr Sınıfı
ms.date: 11/04/2016
f1_keywords:
- CComGITPtr
- ATLBASE/ATL::CComGITPtr
- ATLBASE/ATL::CComGITPtr::CComGITPtr
- ATLBASE/ATL::CComGITPtr::Attach
- ATLBASE/ATL::CComGITPtr::CopyTo
- ATLBASE/ATL::CComGITPtr::Detach
- ATLBASE/ATL::CComGITPtr::GetCookie
- ATLBASE/ATL::CComGITPtr::Revoke
- ATLBASE/ATL::CComGITPtr::m_dwCookie
helpviewer_keywords:
- CComGITPtr class
ms.assetid: af895acb-525a-4555-bb67-b241b7df515b
ms.openlocfilehash: 230eeb1577189d2057e530e1df8ef99c611fb32b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81327834"
---
# <a name="ccomgitptr-class"></a>CComGITPtr Sınıfı

Bu sınıf, arabirim işaretçileri ve genel arabirim tablosu (GIT) ile başa çıkmak için yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class CComGITPtr
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
GIT'de depolanacak arabirim işaretçisinin türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Adı|Açıklama|
|----------|-----------------|
|[CComGITPtr::CComGITPtr](#ccomgitptr)|Oluşturucu.|
|[CComGITPtr::~CComGITPtr](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Adı|Açıklama|
|----------|-----------------|
|[CComGITPtr::Ekle](#attach)|Arabirim işaretçisini genel arabirim tablosuna (GIT) kaydetmek için bu yöntemi arayın.|
|[CComGITPtr::CopyTo](#copyto)|Arabirimi global arabirim tablosundan (GIT) geçirilen işaretçiye kopyalamak için bu yöntemi arayın.|
|[CComGITPtr::Detach](#detach)|Arabirimi `CComGITPtr` nesneden ayırmak için bu yöntemi çağırın.|
|[CComGITPtr::GetCookie](#getcookie)|Çerezi `CComGITPtr` nesneden döndürmek için bu yöntemi çağırın.|
|[CComGITPtr::İptal](#revoke)|Arabirimi global arabirim tablosundan (GIT) kaldırmak için bu yöntemi arayın.|

### <a name="public-operators"></a>Ortak İşleçler

|Adı|Açıklama|
|----------|-----------------|
|[CComGITPtr::operatör DWORD](#operator_dword)|`CComGITPtr` Çerezi nesneden döndürür.|
|[CComGITPtr::operatör =](#operator_eq)|Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Adı|Açıklama|
|----------|-----------------|
|[CComGITPtr::m_dwCookie](#m_dwcookie)|Kurabiye.|

## <a name="remarks"></a>Açıklamalar

Serbest iş parçacığı mareşalini toplayan ve diğer nesnelerden elde edilen arabirim işaretçilerini kullanması gereken nesneler, arabirimlerin doğru şekilde marshaled olduğundan emin olmak için ek adımlar atmalıdır. Genellikle bu, arabirim işaretçilerini GIT'de depolamayı ve her kullanıldığında GIT'den işaretçiyi almayı içerir. Sınıf, `CComGITPtr` GIT'de depolanan arabirim işaretçilerini kullanmanıza yardımcı olmak için sağlanır.

> [!NOTE]
> Küresel arayüz tablosu tesisi yalnızca DCOM sürüm 1.1 ve sonraki sürümlerle Windows 95'te, Windows 98'de, Windows NT 4.0'da Service Pack 3 ve sonraki sürümlerden ve Windows 2000'de kullanılabilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase.h

## <a name="ccomgitptrattach"></a><a name="attach"></a>CComGITPtr::Ekle

Arabirim işaretçisini genel arabirim tablosuna (GIT) kaydetmek için bu yöntemi arayın.

```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```

### <a name="parameters"></a>Parametreler

*P*<br/>
Git'e eklenecek arabirim işaretçisi.

*dwCookie*<br/>
Arabirim işaretçisini tanımlamak için kullanılan çerez.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama oluştururda, GIT geçerli değilse veya çerez NULL'a eşitse bir tasnif hatası oluşur.

## <a name="ccomgitptrccomgitptr"></a><a name="ccomgitptr"></a>CComGITPtr::CComGITPtr

Oluşturucu.

```
CComGITPtr() throw();
CComGITPtr(T* p);
CComGITPtr(const CComGITPtr& git);
explicit CComGITPtr(DWORD dwCookie) throw();
CComGITPtr(CComGITPtr&& rv);
```

### <a name="parameters"></a>Parametreler

*P*<br/>
[içinde] Genel arabirim tablosunda (GIT) depolanacak bir arabirim işaretçisi.

*git*<br/>
[içinde] Varolan `CComGITPtr` bir nesneye başvuru.

*dwCookie*<br/>
[içinde] Arabirim işaretçisini tanımlamak için kullanılan bir tanımlama bilgisi.

*Rv*<br/>
[içinde] Verileri `CComGITPtr` taşımak için kaynak nesne.

### <a name="remarks"></a>Açıklamalar

İsteğe bağlı `CComGITPtr` olarak varolan `CComGITPtr` bir nesneyi kullanarak yeni bir nesne oluşturur.

*RV* kullanan yapıcı bir hareket yapıcıdır. Veriler kaynaktan taşınır, *rv*, ve sonra *rv* temizlenir.

## <a name="ccomgitptrccomgitptr"></a><a name="dtor"></a>CComGITPtr::~CComGITPtr

Yıkıcı.

```
~CComGITPtr() throw();
```

### <a name="remarks"></a>Açıklamalar

[CComGITPtr kullanarak](#revoke)arabirimi global arabirim tablosundan (GIT) kaldırır::İptal edin.

## <a name="ccomgitptrcopyto"></a><a name="copyto"></a>CComGITPtr::CopyTo

Arabirimi global arabirim tablosundan (GIT) geçirilen işaretçiye kopyalamak için bu yöntemi arayın.

```
HRESULT CopyTo(T** pp) const throw();
```

### <a name="parameters"></a>Parametreler

*S*<br/>
Arabirimi almak için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

GIT'deki arabirim geçirilen işaretçiye kopyalanır. İşaretçi, artık gerekli olmadığında arayan tarafından serbest bırakılmalıdır.

## <a name="ccomgitptrdetach"></a><a name="detach"></a>CComGITPtr::Detach

Arabirimi `CComGITPtr` nesneden ayırmak için bu yöntemi çağırın.

```
DWORD Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CComGITPtr` Çerezi nesneden döndürür.

### <a name="remarks"></a>Açıklamalar

CComGITPtr kullanarak arabirimi GIT'den kaldırmak arayana [kalmış::İptal et.](#revoke)

## <a name="ccomgitptrgetcookie"></a><a name="getcookie"></a>CComGITPtr::GetCookie

Çerezi `CComGITPtr` nesneden döndürmek için bu yöntemi çağırın.

```
DWORD GetCookie() const;
```

### <a name="return-value"></a>Dönüş Değeri

Çerezi döndürür.

### <a name="remarks"></a>Açıklamalar

Çerez, arabirimi ve konumunu tanımlamak için kullanılan bir değişkendir.

## <a name="ccomgitptrm_dwcookie"></a><a name="m_dwcookie"></a>CComGITPtr::m_dwCookie

Kurabiye.

```
DWORD m_dwCookie;
```

### <a name="remarks"></a>Açıklamalar

Çerez, arabirimi ve konumunu tanımlamak için kullanılan bir üye değişkendir.

## <a name="ccomgitptroperator-"></a><a name="operator_eq"></a>CComGITPtr::operatör =

Atama işleci.

```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```

### <a name="parameters"></a>Parametreler

*P*<br/>
[içinde] Arabirime işaretçi.

*git*<br/>
[içinde] Bir `CComGITPtr` nesneye başvuru.

*dwCookie*<br/>
[içinde] Arabirim işaretçisini tanımlamak için kullanılan bir tanımlama bilgisi.

*Rv*<br/>
[içinde] Verileri `CComGITPtr` taşımak için.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CComGITPtr` nesneyi döndürür.

### <a name="remarks"></a>Açıklamalar

Varolan bir nesneden `CComGITPtr` veya bir başvurudan genel arabirim tablosuna yeni bir değer atar.

## <a name="ccomgitptroperator-dword"></a><a name="operator_dword"></a>CComGITPtr::operatör DWORD

Nesneyle ilişkili çerezi döndürür. `CComGITPtr`

```
operator DWORD() const;
```

### <a name="remarks"></a>Açıklamalar

Çerez, arabirimi ve konumunu tanımlamak için kullanılan bir değişkendir.

## <a name="ccomgitptrrevoke"></a><a name="revoke"></a>CComGITPtr::İptal

Geçerli arabirimi global arabirim tablosundan (GIT) kaldırmak için bu yöntemi arayın.

```
HRESULT Revoke() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı S_OK veya hatada Bir hata HRESULT verir.

### <a name="remarks"></a>Açıklamalar

Arabirimi GIT'den kaldırır.

## <a name="see-also"></a>Ayrıca bkz.

[Ücretsiz Dişli Mareşal](../../atl/atl-and-the-free-threaded-marshaler.md)<br/>
[Daireler Arasında Arayüzlere Erişim](/windows/win32/com/accessing-interfaces-across-apartments)<br/>
[Genel Arayüz Tablosu Ne Zaman Kullanılır?](/windows/win32/com/when-to-use-the-global-interface-table)<br/>
[Sınıfa Genel Bakış](../../atl/atl-class-overview.md)
