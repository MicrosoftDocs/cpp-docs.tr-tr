---
title: Ccomgıtptr sınıfı
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
ms.openlocfilehash: bf509d027833610e4251c009d4e444dad3fdd5ce
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62246479"
---
# <a name="ccomgitptr-class"></a>Ccomgıtptr sınıfı

Bu sınıf, arabirim işaretçilerini başa çıkmak için yöntemleri ve genel arabirim tablosu (GIT) sağlar.

## <a name="syntax"></a>Sözdizimi

```
template <class T>
class CComGITPtr
```

#### <a name="parameters"></a>Parametreler

*T*<br/>
GİT'te depolanacak arabirim işaretçisi türü.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

|Ad|Açıklama|
|----------|-----------------|
|[CComGITPtr::CComGITPtr](#ccomgitptr)|Oluşturucu.|
|[Ccomgıtptr:: ~ Ccomgıtptr](#dtor)|Yıkıcı.|

### <a name="public-methods"></a>Ortak Yöntemler

|Ad|Açıklama|
|----------|-----------------|
|[CComGITPtr::Attach](#attach)|Arabirim işaretçisi genel arabirim tablosu (GIT) kaydetmek için bu yöntemi çağırın.|
|[CComGITPtr::CopyTo](#copyto)|Arabirim geçirilen işaretçisi genel arabirim tablosundan (GIT) kopyalamak için bu yöntemi çağırın.|
|[CComGITPtr::Detach](#detach)|Arabirimden ilişkisini kaldırmak için bu yöntemi çağırın `CComGITPtr` nesne.|
|[CComGITPtr::GetCookie](#getcookie)|Tanımlama bilgisinden döndürmek için bu yöntemi çağırın `CComGITPtr` nesne.|
|[CComGITPtr::Revoke](#revoke)|Genel arabirim tablosundan (GIT) arabirimi kaldırmak için bu yöntemi çağırın.|

### <a name="public-operators"></a>Ortak İşleçler

|Ad|Açıklama|
|----------|-----------------|
|[CComGITPtr::operator DWORD](#operator_dword)|Tanımlama bilgisinden döndürür `CComGITPtr` nesne.|
|[CComGITPtr::operator =](#operator_eq)|Atama işleci.|

### <a name="public-data-members"></a>Ortak Veri Üyeleri

|Ad|Açıklama|
|----------|-----------------|
|[CComGITPtr::m_dwCookie](#m_dwcookie)|Tanımlama bilgisi.|

## <a name="remarks"></a>Açıklamalar

Ücretsiz iş parçacıklı Sıralayıcı toplama ve diğer nesnelerden elde edilen arabirim işaretçilerini kullanması gereken nesneleri, arabirimler doğru sıralanmış emin olmak için ek adımlar atmanız gerekir. Bu genellikle GİT'te arabirim işaretçilerini depolamak ve işaretçiyi GİT'ten her kullanılışında alma içerir. Sınıf `CComGITPtr` git'te arabirim işaretçilerini kullanmanıza yardımcı olması için sağlanmıştır.

> [!NOTE]
>  Genel arabirim tablosu olanağı, yalnızca DCOM sürüm 1.1 ile Windows 95 ve üzeri, Windows 98, Windows NT 4.0 Service Pack 3 ve üzeri ve Windows 2000 üzerinde kullanılabilir.

## <a name="requirements"></a>Gereksinimler

**Başlık:** atlbase.h

##  <a name="attach"></a>  CComGITPtr::Attach

Arabirim işaretçisi genel arabirim tablosu (GIT) kaydetmek için bu yöntemi çağırın.

```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```

### <a name="parameters"></a>Parametreler

*p*<br/>
GİT'e eklenecek arabirim işaretçisi.

*dwCookie*<br/>
Arabirim işaretçisi tanımlamak için kullanılan tanımlama bilgisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Hata ayıklama yapılarında, onaylama işlemi hatası GIT geçerli değilse veya tanımlama bilgisinin NULL değerine eşit olduğunda meydana gelir.

##  <a name="ccomgitptr"></a>  CComGITPtr::CComGITPtr

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
[in] Genel arabirim tablosu (GIT) depolanması için bir arabirim işaretçisi.

*Git*<br/>
[in] Var olan bir başvuru `CComGITPtr` nesne.

*dwCookie*<br/>
[in] Arabirim işaretçisi tanımlamak için kullanılan tanımlama bilgisi.

*rv*<br/>
[in] Kaynak `CComGITPtr` verileri taşımak için nesne.

### <a name="remarks"></a>Açıklamalar

Yeni bir oluşturur `CComGITPtr` nesne, isteğe bağlı olarak var olan bir kullanarak `CComGITPtr` nesne.

Oluşturucu kullanan *önlemek için rv* bir taşıma Oluşturucu. Veri kaynağından taşınır *önlemek için rv*, ardından *önlemek için rv* temizlenir.

##  <a name="dtor"></a>  Ccomgıtptr:: ~ Ccomgıtptr

Yıkıcı.

```
~CComGITPtr() throw();
```

### <a name="remarks"></a>Açıklamalar

Genel arabirim tablosundan (GIT) arabirim kaldırır kullanarak [CComGITPtr::Revoke](#revoke).

##  <a name="copyto"></a>  CComGITPtr::CopyTo

Arabirim geçirilen işaretçisi genel arabirim tablosundan (GIT) kopyalamak için bu yöntemi çağırın.

```
HRESULT CopyTo(T** pp) const throw();
```

### <a name="parameters"></a>Parametreler

*PP*<br/>
Arabirimi almak için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

GIT arabiriminden geçirilen işaretçisi kopyalanır. Artık gerekli olmadığında arayan tarafından işaretçi serbest bırakılması gerekir.

##  <a name="detach"></a>  CComGITPtr::Detach

Arabirimden ilişkisini kaldırmak için bu yöntemi çağırın `CComGITPtr` nesne.

```
DWORD Detach() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Tanımlama bilgisinden döndürür `CComGITPtr` nesne.

### <a name="remarks"></a>Açıklamalar

GİT'ten arabirimi kaldırmak için çağıranın kadar olan kullanarak [CComGITPtr::Revoke](#revoke).

##  <a name="getcookie"></a>  CComGITPtr::GetCookie

Tanımlama bilgisinden döndürmek için bu yöntemi çağırın `CComGITPtr` nesne.

```
DWORD GetCookie() const;
```

### <a name="return-value"></a>Dönüş Değeri

Tanımlama bilgisini döndürür.

### <a name="remarks"></a>Açıklamalar

Tanımlama bilgisi, bir arabirim ve konumunu tanımlamak için kullanılan bir değişkendir.

##  <a name="m_dwcookie"></a>  CComGITPtr::m_dwCookie

Tanımlama bilgisi.

```
DWORD m_dwCookie;
```

### <a name="remarks"></a>Açıklamalar

Tanımlama bilgisi, bir arabirim ve konumunu tanımlamak için kullanılan bir üye değişkendir.

##  <a name="operator_eq"></a>  CComGITPtr::operator =

Atama işleci.

```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```

### <a name="parameters"></a>Parametreler

*p*<br/>
[in] Bir arabirim işaretçisi.

*Git*<br/>
[in] Bir başvuru bir `CComGITPtr` nesne.

*dwCookie*<br/>
[in] Arabirim işaretçisi tanımlamak için kullanılan tanımlama bilgisi.

*rv*<br/>
[in] `CComGITPtr` Verileri taşımak için.

### <a name="return-value"></a>Dönüş Değeri

Güncelleştirilmiş döndürür `CComGITPtr` nesne.

### <a name="remarks"></a>Açıklamalar

Yeni bir değer atar bir `CComGITPtr` nesne, var olan bir nesne veya bir genel arabirim tablosuna bir başvurudur.

##  <a name="operator_dword"></a>  CComGITPtr::operator DWORD

İle ilişkili tanımlama döndürür `CComGITPtr` nesne.

```
operator DWORD() const;
```

### <a name="remarks"></a>Açıklamalar

Tanımlama bilgisi, bir arabirim ve konumunu tanımlamak için kullanılan bir değişkendir.

##  <a name="revoke"></a>  CComGITPtr::Revoke

Geçerli arabirimi genel arabirim tablosundan (GIT) kaldırmak için bu yöntemi çağırın.

```
HRESULT Revoke() throw();
```

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK veya hatasında bir hata HRESULT döndürür.

### <a name="remarks"></a>Açıklamalar

Arabirim GIT deposundan kaldırır.

## <a name="see-also"></a>Ayrıca bkz.

[Ücretsiz iş parçacıklı Sıralayıcı](../../atl/atl-and-the-free-threaded-marshaler.md)<br/>
[Apartmanlar arasında arabirimi erişme](/windows/desktop/com/accessing-interfaces-across-apartments)<br/>
[Genel arabirim tablosu kullanma zamanı](/windows/desktop/com/when-to-use-the-global-interface-table)<br/>
[Sınıfına genel bakış](../../atl/atl-class-overview.md)
