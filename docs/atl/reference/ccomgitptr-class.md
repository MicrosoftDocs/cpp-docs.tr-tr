---
description: 'Daha fazla bilgi edinin: CComGITPtr Class'
title: CComGITPtr sınıfı
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
ms.openlocfilehash: a457c0dea1679b177b72318d636c856334c85e36
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146646"
---
# <a name="ccomgitptr-class"></a>CComGITPtr sınıfı

Bu sınıf, arabirim işaretçileri ve genel arabirim tablosu (GIT) ile ilgili yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class CComGITPtr
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
GIT içinde depolanacak arabirim işaretçisinin türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComGITPtr:: CComGITPtr](#ccomgitptr)|Oluşturucu.|
|[CComGITPtr:: ~ CComGITPtr](#dtor)|Yok edicisi.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComGITPtr:: Attach](#attach)|Arabirim işaretçisini genel arabirim tablosuna (GIT) kaydetmek için bu yöntemi çağırın.|
|[CComGITPtr:: CopyTo](#copyto)|Arabirimi genel arabirim tablosundan (GIT) geçirilen işaretçiye kopyalamak için bu yöntemi çağırın.|
|[CComGITPtr::D etach](#detach)|Arabirimin nesneden ilişkisini kaldırmak için bu yöntemi çağırın `CComGITPtr` .|
|[CComGITPtr:: GetCookie](#getcookie)|Nesnesinden tanımlama bilgisini döndürmek için bu yöntemi çağırın `CComGITPtr` .|
|[CComGITPtr:: Revoke](#revoke)|Arabirimi genel arabirim tablosundan (GIT) kaldırmak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CComGITPtr:: operator DWORD](#operator_dword)|Nesnesinden tanımlama bilgisini döndürür `CComGITPtr` .|
|[CComGITPtr:: operator =](#operator_eq)|Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComGITPtr:: m_dwCookie](#m_dwcookie)|Tanımlama bilgisi.|

## <a name="remarks"></a>Açıklamalar

Serbest iş parçacıklı sıralayıcıyı toplayan ve diğer nesnelerden elde edilen arabirim işaretçilerinin kullanılması gereken nesneler, arabirimlerin doğru şekilde sıralanmasını sağlamak için ek adımlar almalıdır. Genellikle bu, arabirim işaretçilerinin GIT 'te depolanmasını ve her kullanıldığı zaman GIT 'ten işaretçiyi almanızı içerir. Sınıfı, `CComGITPtr` GIT 'te depolanan arabirim işaretçilerini kullanmanıza yardımcı olmak için sağlanır.

> [!NOTE]
> Genel arabirim tablosu özelliği yalnızca DCOM sürümü 1,1 ve üzeri, Windows 98, Service Pack 3 ve üzeri ile Windows 4,0 NT ve Windows 2000 ile Windows 95 'de kullanılabilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

## <a name="ccomgitptrattach"></a><a name="attach"></a> CComGITPtr:: Attach

Arabirim işaretçisini genel arabirim tablosuna (GIT) kaydetmek için bu yöntemi çağırın.

```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
GIT 'e eklenecek arabirim işaretçisi.

*dwCookie*<br/>
Arabirim işaretçisini tanımlamak için kullanılan tanımlama bilgisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, GIT geçerli değilse veya tanımlama bilgisi NULL değerine eşitse bir onaylama hatası oluşur.

## <a name="ccomgitptrccomgitptr"></a><a name="ccomgitptr"></a> CComGITPtr:: CComGITPtr

Oluşturucu.

```
CComGITPtr() throw();
CComGITPtr(T* p);
CComGITPtr(const CComGITPtr& git);
explicit CComGITPtr(DWORD dwCookie) throw();
CComGITPtr(CComGITPtr&& rv);
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
'ndaki Genel arabirim tablosunda (GIT) depolanacak bir arabirim işaretçisi.

*git*<br/>
'ndaki Varolan bir `CComGITPtr` nesneye başvuru.

*dwCookie*<br/>
'ndaki Arabirim işaretçisini tanımlamak için kullanılan tanımlama bilgisi.

*RV*<br/>
'ndaki `CComGITPtr` Verilerin taşınacağı kaynak nesne.

### <a name="remarks"></a>Açıklamalar

`CComGITPtr`İsteğe bağlı olarak var olan bir nesneyi kullanarak yeni bir nesne oluşturur `CComGITPtr` .

*RV* kullanan Oluşturucu bir taşıma oluşturucusudur. Veriler kaynaktan taşınır, *RV* ve sonra *RV* temizlenir.

## <a name="ccomgitptrccomgitptr"></a><a name="dtor"></a> CComGITPtr:: ~ CComGITPtr

Yok edicisi.

```
~CComGITPtr() throw();
```

### <a name="remarks"></a>Açıklamalar

[CComGITPtr:: Revoke](#revoke)kullanarak arabirimi genel arabirim TABLOSUNDAN (GIT) kaldırır.

## <a name="ccomgitptrcopyto"></a><a name="copyto"></a> CComGITPtr:: CopyTo

Arabirimi genel arabirim tablosundan (GIT) geçirilen işaretçiye kopyalamak için bu yöntemi çağırın.

```
HRESULT CopyTo(T** pp) const throw();
```

### <a name="parameters"></a>Parametreler

*Sy*<br/>
Arabirimi alacak olan işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

GIT 'teki arabirim geçirilen işaretçiye kopyalanır. İşaretçi artık gerekli olmadığında, çağıran tarafından serbest bırakılması gerekir.

## <a name="ccomgitptrdetach"></a><a name="detach"></a> CComGITPtr::D etach

Arabirimin nesneden ilişkisini kaldırmak için bu yöntemi çağırın `CComGITPtr` .

```
DWORD Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Nesnesinden tanımlama bilgisini döndürür `CComGITPtr` .

### <a name="remarks"></a>Açıklamalar

[CComGITPtr:: Revoke](#revoke)kullanarak GIT 'ten arabirimi kaldırmak için çağrıyı yapana kadar.

## <a name="ccomgitptrgetcookie"></a><a name="getcookie"></a> CComGITPtr:: GetCookie

Nesnesinden tanımlama bilgisini döndürmek için bu yöntemi çağırın `CComGITPtr` .

```
DWORD GetCookie() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tanımlama bilgisini döndürür.

### <a name="remarks"></a>Açıklamalar

Tanımlama bilgisi, bir arabirimi ve konumunu tanımlamak için kullanılan bir değişkendir.

## <a name="ccomgitptrm_dwcookie"></a><a name="m_dwcookie"></a> CComGITPtr:: m_dwCookie

Tanımlama bilgisi.

```
DWORD m_dwCookie;
```

### <a name="remarks"></a>Açıklamalar

Tanımlama bilgisi, bir arabirimi ve konumunu tanımlamak için kullanılan bir üye değişkenidir.

## <a name="ccomgitptroperator-"></a><a name="operator_eq"></a> CComGITPtr:: operator =

Atama işleci.

```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```

### <a name="parameters"></a>Parametreler

*Lama*<br/>
'ndaki Bir arabirim işaretçisi.

*git*<br/>
'ndaki Bir `CComGITPtr` nesneye başvuru.

*dwCookie*<br/>
'ndaki Arabirim işaretçisini tanımlamak için kullanılan tanımlama bilgisi.

*RV*<br/>
'ndaki `CComGITPtr` Uygulamasına verileri taşıma.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş nesneyi döndürür `CComGITPtr` .

### <a name="remarks"></a>Açıklamalar

`CComGITPtr`Varolan bir nesneden veya bir genel arabirim tablosuna olan bir başvuruya bir nesneye yeni bir değer atar.

## <a name="ccomgitptroperator-dword"></a><a name="operator_dword"></a> CComGITPtr:: operator DWORD

Nesneyle ilişkili tanımlama bilgisini döndürür `CComGITPtr` .

```
operator DWORD() const;
```

### <a name="remarks"></a>Açıklamalar

Tanımlama bilgisi, bir arabirimi ve konumunu tanımlamak için kullanılan bir değişkendir.

## <a name="ccomgitptrrevoke"></a><a name="revoke"></a> CComGITPtr:: Revoke

Geçerli arabirimi genel arabirim tablosundan (GIT) kaldırmak için bu yöntemi çağırın.

```
HRESULT Revoke() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılı S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Arabirimi GIT 'ten kaldırır.

## <a name="see-also"></a>Ayrıca bkz.

[Ücretsiz Iş parçacıklı Sıralayıcı](../../atl/atl-and-the-free-threaded-marshaler.md)<br/>
[Apartmanlar genelinde arabirimlere erişme](/windows/win32/com/accessing-interfaces-across-apartments)<br/>
[Genel arabirim tablosunun ne zaman kullanılacağı](/windows/win32/com/when-to-use-the-global-interface-table)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
