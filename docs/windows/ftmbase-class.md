---
title: FtmBase sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 09/12/2018
ms.technology:
- cpp-windows
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
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 687fd4f4bd77043bd0b74c7bcc39fb6a496b60be
ms.sourcegitcommit: 87d317ac62620c606464d860aaa9e375a91f4c99
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/14/2018
ms.locfileid: "45601463"
---
# <a name="ftmbase-class"></a>FtmBase Sınıfı

Ücretsiz iş parçacıklı bir Sıralayıcı nesnesini temsil eder.

## <a name="syntax"></a>Sözdizimi

```cpp
class FtmBase : public Microsoft::WRL::Implements<
   Microsoft::WRL::RuntimeClassFlags<WinRtClassicComMix>,
   Microsoft::WRL::CloakedIid<IMarshal> >;
```

## <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için [RuntimeClass sınıfının](runtimeclass-class.md).

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

| Ad                         | Açıklama                                        |
| ---------------------------- | -------------------------------------------------- |
| [FtmBase::FtmBase](#ftmbase) | Yeni bir örneğini başlatır `FtmBase` sınıfı. |

### <a name="public-methods"></a>Ortak Yöntemler

| Ad                                                               | Açıklama                                                                                                                                                          |
| ------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Ftmbase::createglobalınterfacetable](#createglobalinterfacetable) | Bir genel arabirim tablosu (GIT) oluşturur.                                                                                                                              |
| [FtmBase::DisconnectObject](#disconnectobject)                     | Zorla tüm dış bağlantılar kurulmasına nesnenin serbest bırakır. Nesnenin sunucu nesnenin uygulaması kapatmadan önce bu yöntemi çağırır.                |
| [FtmBase::GetMarshalSizeMax](#getmarshalsizemax)                   | Belirtilen nesneyi belirtilen arabirim işaretçisini hazırlamak için gereken bayt sayısı üst sınırı alın.                                                |
| [FtmBase::GetUnmarshalClass](#getunmarshalclass)                   | COM kodu için karşılık gelen proxy içeren DLL bulmak için kullandığı CLSID değerini alır. COM proxy'si başlatılmamış bir örneğini oluşturmak için bu DLL'yi yükler. |
| [Ftmbase::marshalınterface](#marshalinterface)                     | Bir akışa bir proxy nesnesi içinde bazı istemci işlemini başlatmak için gerekli verileri yazar.                                                                          |
| [FtmBase::ReleaseMarshalData](#releasemarshaldata)                 | Bir sıralanmış veri paketi yok eder.                                                                                                                                    |
| [Ftmbase::unmarshalınterface](#unmarshalinterface)                 | Yeni oluşturulan proxy başlatır ve proxy için bir arabirim işaretçisini döndürür.                                                                                    |

### <a name="public-data-members"></a>Ortak Veri Üyeleri

| Ad                                | Açıklama                                       |
| ----------------------------------- | ------------------------------------------------- |
| [FtmBase::marshaller_](#marshaller) | Ücretsiz iş parçacıklı Sıralayıcı bir başvuru içerir. |

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`FtmBase`

## <a name="requirements"></a>Gereksinimler

**Başlık:** ftm.h

**Namespace:** Microsoft::WRL

## <a name="createglobalinterfacetable"></a>Ftmbase::createglobalınterfacetable

Bir genel arabirim tablosu (GIT) oluşturur.

```cpp
static HRESULT CreateGlobalInterfaceTable(
   __out IGlobalInterfaceTable **git
);
```

### <a name="parameters"></a>Parametreler

*Git*  
Bu işlem tamamlandığında bir genel arabirim tablosu işaretçisi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

### <a name="remarks"></a>Açıklamalar

Daha fazla bilgi için `IGlobalInterfaceTable` konudaki `COM Interfaces` , alt konu `COM Reference` MSDN Kitaplığı'nda konu.

## <a name="disconnectobject"></a>FtmBase::DisconnectObject

Zorla tüm dış bağlantılar kurulmasına nesnenin serbest bırakır. Nesnenin sunucu nesnenin uygulaması kapatmadan önce bu yöntemi çağırır.

```cpp
STDMETHODIMP DisconnectObject(
   __in DWORD dwReserved
) override;
```

### <a name="parameters"></a>Parametreler

*dwReserved*  
Gelecekte kullanılmak üzere ayrılmış; sıfır olmalıdır.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="ftmbase"></a>FtmBase::FtmBase

Yeni bir örneğini başlatır `FtmBase` sınıfı.

```cpp
FtmBase();
```

## <a name="getmarshalsizemax"></a>FtmBase::GetMarshalSizeMax

Belirtilen nesneyi belirtilen arabirim işaretçisini hazırlamak için gereken bayt sayısı üst sınırı alın.

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

*riid*  
Sıralanması arabirimi tanımlayıcısını başvuru.

*BD*  
Arabirim işaretçisi; sıralanması NULL olabilir.

*dwDestContext*  
Belirtilen arabirim iptal edilecek olduğu hedef bağlamı.

Bir veya daha fazla MSHCTX numaralandırma değerlerini belirtin.

Şu anda unmarshaling geçerli işlemin (MSHCTX_INPROC) başka bir grup veya geçerli işlem (MSHCTX_LOCAL) ile aynı bilgisayarda başka bir işlem içinde ortaya çıkabilir.

*pvDestContext*  
Gelecekte kullanılmak üzere ayrılmış; NULL olmalıdır.

*mshlflags*  
İstemci işlemine aktarılacak veri sıralanması olup olmadığını belirten bayrak — genellikle bu durum — burada, alınabilir birden çok istemci tarafından genel bir tablo yazılamaz veya okunamaz. Bir veya daha fazla MSHLFLAGS numaralandırma değerlerini belirtin.

*pSize*  
Bu işlem tamamlandığında hazırlama akışa yazılacak veri miktarına üst sınırı için işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde E_FAIL veya e_noınterface.

## <a name="getunmarshalclass"></a>FtmBase::GetUnmarshalClass

COM kodu için karşılık gelen proxy içeren DLL bulmak için kullandığı CLSID değerini alır. COM proxy'si başlatılmamış bir örneğini oluşturmak için bu DLL'yi yükler.

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

*riid*  
Sıralanması arabirimi tanımlayıcısını başvuru.

*BD*  
Sıralanması arabirim işaretçisi; çağıranın istendiği arayüz işaretçisi yoksa NULL olabilir.

*dwDestContext*  
Belirtilen arabirim iptal edilecek olduğu hedef bağlamı.

Bir veya daha fazla MSHCTX numaralandırma değerlerini belirtin.

Unmarshaling ya da geçerli işlemin (MSHCTX_INPROC) başka bir grup veya geçerli işlem (MSHCTX_LOCAL) ile aynı bilgisayarda başka bir işlemde ortaya çıkabilir.

*pvDestContext*  
Gelecekte kullanılmak üzere ayrılmış; NULL olmalıdır.

*mshlflags*  
Bu işlem tamamlandığında CLSID istemci işlemini bir ara sunucu oluşturmak için kullanılacak işaretçi.

*Pcıd*

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, S_FALSE.

## <a name="marshalinterface"></a>Ftmbase::marshalınterface

Bir akışa bir proxy nesnesi içinde bazı istemci işlemini başlatmak için gerekli verileri yazar.

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

*pStm*  
Hazırlama sırasında kullanılmak üzere stream işaretçisi.

*riid*  
Sıralanması arabirimi tanımlayıcısını başvuru. Bu arabirim nesnesinden türetilmesi `IUnknown` arabirimi.

*BD*  
İşaretçi sıralanması arabirim işaretçisi için; çağıranın istendiği arayüz işaretçisi yoksa NULL olabilir.

*dwDestContext*  
Belirtilen arabirim iptal edilecek olduğu hedef bağlamı.

Bir veya daha fazla MSHCTX numaralandırma değerlerini belirtin.

Unmarshaling, geçerli işlemin (MSHCTX_INPROC) başka bir grup veya geçerli işlem (MSHCTX_LOCAL) ile aynı bilgisayarda başka bir işlemde ortaya çıkabilir.

*pvDestContext*  
Gelecekte kullanılmak üzere ayrılmış; sıfır olmalıdır.

*mshlflags*  
İstemci işlemine aktarılacak veri sıralanması olup olmadığını belirtir: genellikle bu durum — burada da alınabilir birden çok istemci tarafından genel bir tablo yazılamaz veya okunamaz.

### <a name="return-value"></a>Dönüş Değeri

Arabirim işaretçisi S_OK başarılı bir şekilde sıralanır.

Belirtilen arabirim e_noınterface desteklenmiyor.

Akış STG_E_MEDIUMFULL dolu.

E_FAIL işlemi başarısız oldu.

## <a name="marshaller"></a>FtmBase::marshaller_

Ücretsiz iş parçacıklı Sıralayıcı bir başvuru içerir.

```cpp
Microsoft::WRL::ComPtr<IMarshal> marshaller_; ;
```

## <a name="releasemarshaldata"></a>FtmBase::ReleaseMarshalData

Bir sıralanmış veri paketi yok eder.

```cpp
STDMETHODIMP ReleaseMarshalData(
   __in IStream *pStm
) override;
```

### <a name="parameters"></a>Parametreler

*pStm*  
Yok edilecek veri paketi içeren bir akışa yönelik işaretçi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, HRESULT hata olduğunu gösterir.

## <a name="unmarshalinterface"></a>Ftmbase::unmarshalınterface

Yeni oluşturulan proxy başlatır ve proxy için bir arabirim işaretçisini döndürür.

```cpp
STDMETHODIMP UnmarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __deref_out void **ppv
) override;
```

### <a name="parameters"></a>Parametreler

*pStm*  
Arabirim işaretçisi iptal edilecek olduğu akışa yönelik işaretçi.

*riid*  
İptal edilecek arabirimi tanımlayıcısını başvuru.

*ppv*  
Bu işlem tamamlandığında, istenen arabirim işaretçisi alır bir işaretçi değişkeninin adresini *riid*. Bu işlem başarılı olursa **ppv* iptal edilecek arabiriminin istenen arabirim işaretçisi içerir.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde e_noınterface veya E_FAIL.
