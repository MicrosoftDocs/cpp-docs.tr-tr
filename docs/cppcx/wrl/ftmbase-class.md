---
title: FtmBase Sınıfı
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase
- ftm/Microsoft::WRL::FtmBaseCreateGlobalInterfaceTable
- ftm/Microsoft::WRL::FtmBase::DisconnectObject
- ftm/Microsoft::WRL::FtmBase::FtmBase
- ftm/Microsoft::WRL::FtmBase::GetMarshalSizeMax
- ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass
- ftm/Microsoft::WRL::FtmBase::MarshalInterface
- ftm/Microsoft::WRL::FtmBase::marshaller_
- ftm/Microsoft::WRL::FtmBase::ReleaseMarshalData
- ftm/Microsoft::WRL::FtmBase::UnmarshalInterface
helpviewer_keywords:
- Microsoft::WRL::FtmBase class
- Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable method
- Microsoft::WRL::FtmBase::DisconnectObject method
- Microsoft::WRL::FtmBase::FtmBase, constructor
- Microsoft::WRL::FtmBase::GetMarshalSizeMax method
- Microsoft::WRL::FtmBase::GetUnmarshalClass method
- Microsoft::WRL::FtmBase::MarshalInterface method
- Microsoft::WRL::FtmBase::marshaller_ data member
- Microsoft::WRL::FtmBase::ReleaseMarshalData method
- Microsoft::WRL::FtmBase::UnmarshalInterface method
ms.assetid: 275f3b71-2975-4f92-89e7-d351e96496df
ms.openlocfilehash: d37cdddda8cf8894016ed80b9055fe106b1600f7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371510"
---
# <a name="ftmbase-class"></a>FtmBase Sınıfı

Serbest iş parçacığı mareşal nesnesi temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class FtmBase :
    public Microsoft::WRL::Implements<
        Microsoft::WRL::RuntimeClassFlags<WinRtClassicComMix>,
        Microsoft::WRL::CloakedIid<IMarshal>
    >;
```

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [RuntimeClass Class'a](runtimeclass-class.md)bakın.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

| Adı                         | Açıklama                                        |
| ---------------------------- | -------------------------------------------------- |
| [FtmBase::FtmBase](#ftmbase) | `FtmBase` sınıfının yeni bir örneğini başlatır. |

### <a name="public-methods"></a>Ortak Yöntemler

| Adı                                                               | Açıklama                                                                                                                                                          |
| ------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [FtmBase::CreateGlobalInterfaceTable](#createglobalinterfacetable) | Genel arabirim tablosu (GIT) oluşturur.                                                                                                                              |
| [FtmBase::DisconnectObject](#disconnectobject)                     | Bir nesneye yapılan tüm dış bağlantıları zorla söken. Nesnenin sunucusu kapatmadan önce nesnenin bu yöntemin uygulanmasını çağırır.                |
| [FtmBase::GetMarshalSizeMax](#getmarshalsizemax)                   | Belirtilen nesne üzerinde belirtilen arabirim işaretçisi mareşal için gerekli bayt sayısı üst sınır alın.                                                |
| [FtmBase::GetUnmarshalClass](#getunmarshalclass)                   | COM'un ilgili proxy kodunu içeren DLL'yi bulmak için kullandığı CLSID'yi alır. COM, proxy'nin başharflenmemiş bir örneğini oluşturmak için bu DLL'yi yükler. |
| [FtmBase::MarshalInterface](#marshalinterface)                     | Bir akışa, bazı istemci işleminde proxy nesnesini başlatması için gereken verileri yazar.                                                                          |
| [FtmBase::ReleaseMarshalData](#releasemarshaldata)                 | Marshaled veri paketini yok eder.                                                                                                                                    |
| [FtmBase::UnmarshalInterface](#unmarshalinterface)                 | Yeni oluşturulan proxy'yi başolarak karşılar ve bu proxy'ye bir arabirim işaretçisi döndürür.                                                                                    |

### <a name="public-data-members"></a>Ortak Veri Üyeleri

| Adı                                | Açıklama                                       |
| ----------------------------------- | ------------------------------------------------- |
| [FtmBase::marshaller_](#marshaller) | Serbest dişli mareşal bir referans tutar. |

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`FtmBase`

## <a name="requirements"></a>Gereksinimler

**Başlık:** ftm.h

**Ad alanı:** Microsoft::WRL

## <a name="ftmbasecreateglobalinterfacetable"></a><a name="createglobalinterfacetable"></a>FtmBase::CreateGlobalInterfaceTable

Genel arabirim tablosu (GIT) oluşturur.

```cpp
static HRESULT CreateGlobalInterfaceTable(
   __out IGlobalInterfaceTable **git
);
```

### <a name="parameters"></a>Parametreler

*git*<br/>
Bu işlem tamamlandığında, genel arabirim tablosuna işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi `IGlobalInterfaceTable` için, `COM Interfaces` MSDN `COM Reference` Kitaplığı'ndaki konunun alt başlığındaki konuya bakın.

## <a name="ftmbasedisconnectobject"></a><a name="disconnectobject"></a>FtmBase::DisconnectObject

Bir nesneye yapılan tüm dış bağlantıları zorla söken. Nesnenin sunucusu kapatmadan önce nesnenin bu yöntemin uygulanmasını çağırır.

```cpp
STDMETHODIMP DisconnectObject(
   __in DWORD dwReserved
) override;
```

### <a name="parameters"></a>Parametreler

*dwAyrılmış*<br/>
İleride kullanım için ayrılmış; sıfır olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="ftmbaseftmbase"></a><a name="ftmbase"></a>FtmBase::FtmBase

`FtmBase` sınıfının yeni bir örneğini başlatır.

```cpp
FtmBase();
```

## <a name="ftmbasegetmarshalsizemax"></a><a name="getmarshalsizemax"></a>FtmBase::GetMarshalSizeMax

Belirtilen nesne üzerinde belirtilen arabirim işaretçisi mareşal için gerekli bayt sayısı üst sınır alın.

```cpp
STDMETHODIMP GetMarshalSizeMax(
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags,
   __out DWORD *pSize
) override;
```

### <a name="parameters"></a>Parametreler

*Riid*<br/>
Marshaled için arabirimin tanımlayıcısına başvuru.

*Pv*<br/>
Arabirim işaretçisi marshaled olmak; NULL olabilir.

*dwDestBağlam*<br/>
Belirtilen arabirimin alınacağı hedef bağlam.

Bir veya daha fazla MSHCTX numaralandırma değeri belirtin.

Şu anda, görevden alma, geçerli işlemin başka bir dairesinde (MSHCTX_INPROC) veya geçerli işlemle aynı bilgisayarda başka bir işlemde (MSHCTX_LOCAL) oluşabilir.

*pvDestContext*<br/>
İleride kullanım için ayrılmış; NULL olmalıdır.

*mshlflags*<br/>
Marshaled edilecek verilerin istemci işlemine (tipik durum) geri aktarılıp aktarılmayacağını veya birden çok istemci tarafından alınabileceği genel bir tabloya yazılmının olup olmadığını belirten bayrak. Bir veya daha fazla MSHLFLAGS numaralandırma değeri belirtin.

*pSize*<br/>
Bu işlem tamamlandığında, mareşal akışına yazılması gereken veri miktarı üzerinde üst sınırı işaretle.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, E_FAIL veya E_NOINTERFACE.

## <a name="ftmbasegetunmarshalclass"></a><a name="getunmarshalclass"></a>FtmBase::GetUnmarshalClass

COM'un ilgili proxy kodunu içeren DLL'yi bulmak için kullandığı CLSID'yi alır. COM, proxy'nin başharflenmemiş bir örneğini oluşturmak için bu DLL'yi yükler.

```cpp
STDMETHODIMP GetUnmarshalClass(
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags,
   __out CLSID *pCid
) override;
```

### <a name="parameters"></a>Parametreler

*Riid*<br/>
Marshaled için arabirimin tanımlayıcısına başvuru.

*Pv*<br/>
İşaretçi arabirimi için marshaled olmak; arayan istenilen arabirime işaretçisi yoksa NULL olabilir.

*dwDestBağlam*<br/>
Belirtilen arabirimin alınacağı hedef bağlam.

Bir veya daha fazla MSHCTX numaralandırma değeri belirtin.

Unmarshaling geçerli işlemin başka bir dairede (MSHCTX_INPROC) veya geçerli işlem (MSHCTX_LOCAL) ile aynı bilgisayarda başka bir işlem oluşabilir.

*pvDestContext*<br/>
İleride kullanım için ayrılmış; NULL olmalıdır.

*mshlflags*<br/>
Bu işlem tamamlandığında, istemci işleminde bir proxy oluşturmak için kullanılmak üzere CLSID işaretçisi.

*pCid*

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, S_FALSE.

## <a name="ftmbasemarshalinterface"></a><a name="marshalinterface"></a>FtmBase::MarshalInterface

Bir akışa, bazı istemci işleminde proxy nesnesini başlatması için gereken verileri yazar.

```cpp
STDMETHODIMP MarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags
) override;
```

### <a name="parameters"></a>Parametreler

*pStm*<br/>
Mareşallik sırasında kullanılacak akışı işaretçi.

*Riid*<br/>
Marshaled için arabirimin tanımlayıcısına başvuru. Bu arabirim `IUnknown` arabirimden türetilmelidir.

*Pv*<br/>
İşaretçi, mareşalolarak işaretedilecek arabirim işaretçisine; arayan istenilen arabirime işaretçisi yoksa NULL olabilir.

*dwDestBağlam*<br/>
Belirtilen arabirimin alınacağı hedef bağlam.

Bir veya daha fazla MSHCTX numaralandırma değeri belirtin.

Unmarshaling geçerli işlemin başka bir dairede oluşabilir (MSHCTX_INPROC) veya geçerli işlem (MSHCTX_LOCAL) ile aynı bilgisayarda başka bir işlem.

*pvDestContext*<br/>
İleride kullanım için ayrılmış; sıfır olmalıdır.

*mshlflags*<br/>
Marshaled edilecek verilerin istemci işlemine (tipik durum) geri aktarılıp aktarılmayacağını veya birden çok istemci tarafından alınabileceği genel bir tabloya yazılmı belirtir.

### <a name="return-value"></a>Dönüş Değeri

S_OK Arabirim işaretçisi başarıyla marshaled edildi.

E_NOINTERFACE Belirtilen arabirim desteklenmez.

STG_E_MEDIUMFULL Akış dolu.

E_FAIL İşlem başarısız oldu.

## <a name="ftmbasemarshaller_"></a><a name="marshaller"></a>FtmBase::marshaller_

Serbest dişli mareşal bir referans tutar.

```cpp
Microsoft::WRL::ComPtr<IMarshal> marshaller_; ;
```

## <a name="ftmbasereleasemarshaldata"></a><a name="releasemarshaldata"></a>FtmBase::ReleaseMarshalData

Marshaled veri paketini yok eder.

```cpp
STDMETHODIMP ReleaseMarshalData(
   __in IStream *pStm
) override;
```

### <a name="parameters"></a>Parametreler

*pStm*<br/>
Yok edilecek veri paketini içeren bir akışı işaretçi.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="ftmbaseunmarshalinterface"></a><a name="unmarshalinterface"></a>FtmBase::UnmarshalInterface

Yeni oluşturulan proxy'yi başolarak karşılar ve bu proxy'ye bir arabirim işaretçisi döndürür.

```cpp
STDMETHODIMP UnmarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __deref_out void **ppv
) override;
```

### <a name="parameters"></a>Parametreler

*pStm*<br/>
Arabirim işaretçisinin alınıp çıkarılabilmek için akışı işaretçi.

*Riid*<br/>
Atanacak arabirimin tanımlayıcısına başvuru.

*Ppv*<br/>
Bu işlem tamamlandığında, *riid'de*istenen arabirim işaretçisini alan bir işaretçi değişkeninin adresi. Bu işlem başarılı olursa, **ppv* unmarshaled olmak için arabirimin istenen arabirim işaretçisi içerir.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, E_NOINTERFACE veya E_FAIL.
