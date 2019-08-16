---
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
ms.openlocfilehash: 00265cc445191a5a539ab21d6f64b255849495e9
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69497271"
---
# <a name="ccomgitptr-class"></a>CComGITPtr sınıfı

Bu sınıf, arabirim işaretçileri ve genel arabirim tablosu (GIT) ile ilgili yöntemler sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class CComGITPtr
```

#### <a name="parameters"></a>Parametreler

*ŞI*<br/>
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
|[CComGITPtr::D etach](#detach)|Arabirimin `CComGITPtr` nesneden ilişkisini kaldırmak için bu yöntemi çağırın.|
|[CComGITPtr:: GetCookie](#getcookie)|`CComGITPtr` Nesnesinden tanımlama bilgisini döndürmek için bu yöntemi çağırın.|
|[CComGITPtr:: Revoke](#revoke)|Arabirimi genel arabirim tablosundan (GIT) kaldırmak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CComGITPtr:: operator DWORD](#operator_dword)|`CComGITPtr` Nesnesinden tanımlama bilgisini döndürür.|
|[CComGITPtr:: operator =](#operator_eq)|Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComGITPtr:: m_dwCookie](#m_dwcookie)|Tanımlama bilgisi.|

## <a name="remarks"></a>Açıklamalar

Serbest iş parçacıklı sıralayıcıyı toplayan ve diğer nesnelerden elde edilen arabirim işaretçilerinin kullanılması gereken nesneler, arabirimlerin doğru şekilde sıralanmasını sağlamak için ek adımlar almalıdır. Genellikle bu, arabirim işaretçilerinin GIT 'te depolanmasını ve her kullanıldığı zaman GIT 'ten işaretçiyi almanızı içerir. Sınıfı `CComGITPtr` , GIT 'te depolanan arabirim işaretçilerini kullanmanıza yardımcı olmak için sağlanır.

> [!NOTE]
>  Genel arabirim tablosu özelliği yalnızca DCOM sürümü 1,1 ve üzeri, Windows 98, Service Pack 3 ve üzeri ile Windows 4,0 NT ve Windows 2000 ile Windows 95 'de kullanılabilir.

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** atlbase. h

##  <a name="attach"></a>CComGITPtr:: Attach

Arabirim işaretçisini genel arabirim tablosuna (GIT) kaydetmek için bu yöntemi çağırın.

```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
GIT 'e eklenecek arabirim işaretçisi.

*dwCookie*<br/>
Arabirim işaretçisini tanımlamak için kullanılan tanımlama bilgisi.

### <a name="return-value"></a>Dönüş Değeri

Başarı durumunda S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, GIT geçerli değilse veya tanımlama bilgisi NULL değerine eşitse bir onaylama hatası oluşur.

##  <a name="ccomgitptr"></a>CComGITPtr:: CComGITPtr

Oluşturucu.

```
CComGITPtr() throw();
CComGITPtr(T* p);
CComGITPtr(const CComGITPtr& git);
explicit CComGITPtr(DWORD dwCookie) throw();
CComGITPtr(CComGITPtr&& rv);
```

### <a name="parameters"></a>Parametreler

*p*<br/>
'ndaki Genel arabirim tablosunda (GIT) depolanacak bir arabirim işaretçisi.

*Git@@*<br/>
'ndaki Varolan `CComGITPtr` bir nesneye başvuru.

*dwCookie*<br/>
'ndaki Arabirim işaretçisini tanımlamak için kullanılan tanımlama bilgisi.

*RV*<br/>
'ndaki Verilerin taşınacağı `CComGITPtr` kaynak nesne.

### <a name="remarks"></a>Açıklamalar

İsteğe bağlı olarak `CComGITPtr` var olan `CComGITPtr` bir nesneyi kullanarak yeni bir nesne oluşturur.

*RV* kullanan Oluşturucu bir taşıma oluşturucusudur. Veriler kaynaktan taşınır, *RV*ve sonra *RV* temizlenir.

##  <a name="dtor"></a>CComGITPtr:: ~ CComGITPtr

Yok edicisi.

```
~CComGITPtr() throw();
```

### <a name="remarks"></a>Açıklamalar

[CComGITPtr:: Revoke](#revoke)kullanarak arabirimi genel arabirim TABLOSUNDAN (GIT) kaldırır.

##  <a name="copyto"></a>CComGITPtr:: CopyTo

Arabirimi genel arabirim tablosundan (GIT) geçirilen işaretçiye kopyalamak için bu yöntemi çağırın.

```
HRESULT CopyTo(T** pp) const throw();
```

### <a name="parameters"></a>Parametreler

*Sy*<br/>
Arabirimi alacak olan işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarı durumunda S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

GIT 'teki arabirim geçirilen işaretçiye kopyalanır. İşaretçi artık gerekli olmadığında, çağıran tarafından serbest bırakılması gerekir.

##  <a name="detach"></a>CComGITPtr::D etach

Arabirimin `CComGITPtr` nesneden ilişkisini kaldırmak için bu yöntemi çağırın.

```
DWORD Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

`CComGITPtr` Nesnesinden tanımlama bilgisini döndürür.

### <a name="remarks"></a>Açıklamalar

[CComGITPtr:: Revoke](#revoke)kullanarak GIT 'ten arabirimi kaldırmak için çağrıyı yapana kadar.

##  <a name="getcookie"></a>CComGITPtr:: GetCookie

`CComGITPtr` Nesnesinden tanımlama bilgisini döndürmek için bu yöntemi çağırın.

```
DWORD GetCookie() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tanımlama bilgisini döndürür.

### <a name="remarks"></a>Açıklamalar

Tanımlama bilgisi, bir arabirimi ve konumunu tanımlamak için kullanılan bir değişkendir.

##  <a name="m_dwcookie"></a>CComGITPtr:: m_dwCookie

Tanımlama bilgisi.

```
DWORD m_dwCookie;
```

### <a name="remarks"></a>Açıklamalar

Tanımlama bilgisi, bir arabirimi ve konumunu tanımlamak için kullanılan bir üye değişkenidir.

##  <a name="operator_eq"></a>CComGITPtr:: operator =

Atama işleci.

```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```

### <a name="parameters"></a>Parametreler

*p*<br/>
'ndaki Bir arabirim işaretçisi.

*Git@@*<br/>
'ndaki Bir `CComGITPtr` nesneye başvuru.

*dwCookie*<br/>
'ndaki Arabirim işaretçisini tanımlamak için kullanılan tanımlama bilgisi.

*RV*<br/>
'ndaki `CComGITPtr` Uygulamasına verileri taşıma.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş `CComGITPtr` nesneyi döndürür.

### <a name="remarks"></a>Açıklamalar

Varolan bir nesneden veya bir genel `CComGITPtr` arabirim tablosuna olan bir başvuruya bir nesneye yeni bir değer atar.

##  <a name="operator_dword"></a>CComGITPtr:: operator DWORD

`CComGITPtr` Nesneyle ilişkili tanımlama bilgisini döndürür.

```
operator DWORD() const;
```

### <a name="remarks"></a>Açıklamalar

Tanımlama bilgisi, bir arabirimi ve konumunu tanımlamak için kullanılan bir değişkendir.

##  <a name="revoke"></a>CComGITPtr:: Revoke

Geçerli arabirimi genel arabirim tablosundan (GIT) kaldırmak için bu yöntemi çağırın.

```
HRESULT Revoke() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarı durumunda S_OK veya hata durumunda HRESULT hatası döndürür.

### <a name="remarks"></a>Açıklamalar

Arabirimi GIT 'ten kaldırır.

## <a name="see-also"></a>Ayrıca bkz.

[Ücretsiz Iş parçacıklı Sıralayıcı](../../atl/atl-and-the-free-threaded-marshaler.md)<br/>
[Apartmanlar genelinde arabirimlere erişme](/windows/win32/com/accessing-interfaces-across-apartments)<br/>
[Genel arabirim tablosunun ne zaman kullanılacağı](/windows/win32/com/when-to-use-the-global-interface-table)<br/>
[Sınıfa genel bakış](../../atl/atl-class-overview.md)
