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
ms.openlocfilehash: f28a850c365bc9a75d8e5b100e5e5cc0a1c5dc10
ms.sourcegitcommit: 6b3d793f0ef3bbb7eefaf9f372ba570fdfe61199
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/15/2020
ms.locfileid: "86404570"
---
# <a name="ftmbase-class"></a>FtmBase Sınıfı

Serbest iş parçacıklı Sıralayıcı nesnesini temsil eder.

## <a name="syntax"></a>Syntax

```cpp
class FtmBase :
    public Microsoft::WRL::Implements<
        Microsoft::WRL::RuntimeClassFlags<WinRtClassicComMix>,
        Microsoft::WRL::CloakedIid<IMarshal>
    >;
```

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [RuntimeClass Sınıfı](runtimeclass-class.md).

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

| Ad                         | Açıklama                                        |
| ---------------------------- | -------------------------------------------------- |
| [FtmBase:: FtmBase](#ftmbase) | `FtmBase` sınıfının yeni bir örneğini başlatır. |

### <a name="public-methods"></a>Ortak Yöntemler

| Ad                                                               | Açıklama                                                                                                                                                          |
| ------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [FtmBase:: CreateGlobalInterfaceTable](#createglobalinterfacetable) | Genel arabirim tablosu (GIT) oluşturur.                                                                                                                              |
| [FtmBase::D isconnectObject](#disconnectobject)                     | Tüm dış bağlantıları bir nesneye zorla yayınlar. Nesnenin sunucusu, kapanmadan önce nesnenin bu yöntemin uygulamasını çağırır.                |
| [FtmBase:: GetMarshalSizeMax](#getmarshalsizemax)                   | Belirtilen nesne üzerinde belirtilen arabirim işaretçisini sıralamak için gereken bayt sayısıyla üst sınırı alın.                                                |
| [FtmBase:: GetUnmarshalClass](#getunmarshalclass)                   | Karşılık gelen ara sunucu için kodu içeren DLL 'yi bulmak için COM tarafından kullanılan CLSID 'yi alır. COM, başlatılmamış bir proxy örneğini oluşturmak için bu DLL 'yi yükler. |
| [FtmBase:: MarshalInterface](#marshalinterface)                     | Bazı istemci işlemlerinde bir proxy nesnesini başlatmak için gereken verileri akışa yazar.                                                                          |
| [FtmBase:: ReleaseMarshalData](#releasemarshaldata)                 | Sıralanmış bir veri paketini yok eder.                                                                                                                                    |
| [FtmBase:: UnmarshalInterface](#unmarshalinterface)                 | Yeni oluşturulan bir proxy başlatır ve bu ara sunucuya bir arabirim işaretçisi döndürür.                                                                                    |

### <a name="public-data-members"></a>Ortak Veri Üyeleri

| Ad                                | Açıklama                                       |
| ----------------------------------- | ------------------------------------------------- |
| [FtmBase:: marshaller_](#marshaller) | , Ücretsiz iş parçacıklı Sıralayıcı başvurusunu tutar. |

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`FtmBase`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** FTM. h

**Ad alanı:** Microsoft:: WRL

## <a name="ftmbasecreateglobalinterfacetable"></a><a name="createglobalinterfacetable"></a>FtmBase:: CreateGlobalInterfaceTable

Genel arabirim tablosu (GIT) oluşturur.

```cpp
static HRESULT CreateGlobalInterfaceTable(
   __out IGlobalInterfaceTable **git
);
```

### <a name="parameters"></a>Parametreler

*Git@@*<br/>
Bu işlem tamamlandığında, genel arabirim tablosuna yönelik bir işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için bkz. [`IGlobalInterfaceTable`](https://docs.microsoft.com/windows/win32/api/objidl/nn-objidl-iglobalinterfacetable).

## <a name="ftmbasedisconnectobject"></a><a name="disconnectobject"></a>FtmBase::D isconnectObject

Tüm dış bağlantıları bir nesneye zorla yayınlar. Nesnenin sunucusu, kapanmadan önce nesnenin bu yöntemin uygulamasını çağırır.

```cpp
STDMETHODIMP DisconnectObject(
   __in DWORD dwReserved
) override;
```

### <a name="parameters"></a>Parametreler

*Dwayrýlmýþ*<br/>
Gelecekte kullanılmak üzere ayrılmıştır; sıfır olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="ftmbaseftmbase"></a><a name="ftmbase"></a>FtmBase:: FtmBase

`FtmBase` sınıfının yeni bir örneğini başlatır.

```cpp
FtmBase();
```

## <a name="ftmbasegetmarshalsizemax"></a><a name="getmarshalsizemax"></a>FtmBase:: GetMarshalSizeMax

Belirtilen nesne üzerinde belirtilen arabirim işaretçisini sıralamak için gereken bayt sayısıyla üst sınırı alın.

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

*riıd*<br/>
Sıralanabilen arabirimin tanımlayıcısına başvuru.

*bakın*<br/>
Sıraya eklenecek arabirim işaretçisi; NULL olabilir.

*dwDestContext*<br/>
Belirtilen arabirimin sıralanmakta olduğu hedef bağlam.

Bir veya daha fazla MSHCTX numaralandırma değeri belirtin.

Şu anda, sıralama kaldırma işlemi geçerli işlemin başka bir grubu (MSHCTX_INPROC) veya geçerli işlemle aynı bilgisayardaki başka bir işlemde (MSHCTX_LOCAL) olabilir.

*pvDestContext*<br/>
Gelecekte kullanılmak üzere ayrılmıştır; NULL olmalıdır.

*mshlflags*<br/>
Sıralanmakta olan verilerin istemci işlemine (tipik durum) geri aktarılmak veya bir genel tabloya yazılması, burada birden çok istemci tarafından alınabileceği belirten bayrak. Bir veya daha fazla MSHLFLAGS numaralandırma değeri belirtin.

*Psıze*<br/>
Bu işlem tamamlandığında, hazırlama akışına yazılacak veri miktarına üst sınır işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, E_FAIL veya E_NOINTERFACE.

## <a name="ftmbasegetunmarshalclass"></a><a name="getunmarshalclass"></a>FtmBase:: GetUnmarshalClass

Karşılık gelen ara sunucu için kodu içeren DLL 'yi bulmak için COM tarafından kullanılan CLSID 'yi alır. COM, başlatılmamış bir proxy örneğini oluşturmak için bu DLL 'yi yükler.

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

*riıd*<br/>
Sıralanabilen arabirimin tanımlayıcısına başvuru.

*bakın*<br/>
Sıraya eklenecek arabirime yönelik işaretçi; çağıranın istenen arabirime yönelik bir işaretçisi yoksa NULL olabilir.

*dwDestContext*<br/>
Belirtilen arabirimin sıralanmakta olduğu hedef bağlam.

Bir veya daha fazla MSHCTX numaralandırma değeri belirtin.

Sıralama geri alma işlemi geçerli işlemin başka bir grubu (MSHCTX_INPROC) ya da geçerli işlemle aynı bilgisayardaki başka bir işlemde (MSHCTX_LOCAL) olabilir.

*pvDestContext*<br/>
Gelecekte kullanılmak üzere ayrılmıştır; NULL olmalıdır.

*mshlflags*<br/>
Bu işlem tamamlandığında, istemci işleminde bir ara sunucu oluşturmak için kullanılacak CLSID 'nin işaretçisi.

*PCID*

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, S_FALSE.

## <a name="ftmbasemarshalinterface"></a><a name="marshalinterface"></a>FtmBase:: MarshalInterface

Bazı istemci işlemlerinde bir proxy nesnesini başlatmak için gereken verileri akışa yazar.

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
Sıralama sırasında kullanılacak akışa yönelik işaretçi.

*riıd*<br/>
Sıralanabilen arabirimin tanımlayıcısına başvuru. Bu arabirimin arabiriminden türetilmesi gerekir `IUnknown` .

*bakın*<br/>
Sıraya eklenecek arabirim işaretçisine yönelik işaretçi; çağıranın istenen arabirime yönelik bir işaretçisi yoksa NULL olabilir.

*dwDestContext*<br/>
Belirtilen arabirimin sıralanmakta olduğu hedef bağlam.

Bir veya daha fazla MSHCTX numaralandırma değeri belirtin.

Sıralama geri alma işlemi, geçerli işlemin (MSHCTX_INPROC) veya geçerli işlemle aynı bilgisayardaki başka bir işlemin (MSHCTX_LOCAL) başka bir yerinde gerçekleşebilir.

*pvDestContext*<br/>
Gelecekte kullanılmak üzere ayrılmıştır; sıfır olmalıdır.

*mshlflags*<br/>
Sıralanmak üzere verilerin istemci işlemine (tipik durum) geri aktarılmak veya bir genel tabloya yazılması, burada birden çok istemci tarafından alınabileceği belirtir.

### <a name="return-value"></a>Dönüş Değeri

Arabirim işaretçisinin başarıyla sıralanmıştı S_OK.

Belirtilen arabirim E_NOINTERFACE desteklenmiyor.

Akış dolu STG_E_MEDIUMFULL.

İşlem başarısız E_FAIL.

## <a name="ftmbasemarshaller_"></a><a name="marshaller"></a>FtmBase:: marshaller_

, Ücretsiz iş parçacıklı Sıralayıcı başvurusunu tutar.

```cpp
Microsoft::WRL::ComPtr<IMarshal> marshaller_; ;
```

## <a name="ftmbasereleasemarshaldata"></a><a name="releasemarshaldata"></a>FtmBase:: ReleaseMarshalData

Sıralanmış bir veri paketini yok eder.

```cpp
STDMETHODIMP ReleaseMarshalData(
   __in IStream *pStm
) override;
```

### <a name="parameters"></a>Parametreler

*pStm*<br/>
Yok edilecek veri paketini içeren bir akışa yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, hatayı gösteren bir HRESULT.

## <a name="ftmbaseunmarshalinterface"></a><a name="unmarshalinterface"></a>FtmBase:: UnmarshalInterface

Yeni oluşturulan bir proxy başlatır ve bu ara sunucuya bir arabirim işaretçisi döndürür.

```cpp
STDMETHODIMP UnmarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __deref_out void **ppv
) override;
```

### <a name="parameters"></a>Parametreler

*pStm*<br/>
Arabirim işaretçisinin sıralanamadı olduğu akışa yönelik işaretçi.

*riıd*<br/>
Sıralanmayan arabirimin tanımlayıcısına başvuru.

*PPV*<br/>
Bu işlem tamamlandığında, *riid*içinde istenen arabirim işaretçisini alan bir işaretçi değişkeninin adresi. Bu işlem başarılı olursa, **PPV* , arabirimin istenen arabirim işaretçisini sıralanamadı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, E_NOINTERFACE veya E_FAIL.
