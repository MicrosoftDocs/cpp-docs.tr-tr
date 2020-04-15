---
title: AsyncBase Sınıfı
ms.date: 10/08/2018
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase
- async/Microsoft::WRL::AsyncBase::AsyncBase
- async/Microsoft::WRL::AsyncBase::Cancel
- async/Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall
- async/Microsoft::WRL::AsyncBase::CheckValidStateForResultsCall
- async/Microsoft::WRL::AsyncBase::Close
- async/Microsoft::WRL::AsyncBase::ContinueAsyncOperation
- async/Microsoft::WRL::AsyncBase::CurrentStatus
- async/Microsoft::WRL::AsyncBase::ErrorCode
- async/Microsoft::WRL::AsyncBase::FireCompletion
- async/Microsoft::WRL::AsyncBase::FireProgress
- async/Microsoft::WRL::AsyncBase::get_ErrorCode
- async/Microsoft::WRL::AsyncBase::get_Id
- async/Microsoft::WRL::AsyncBase::get_Status
- async/Microsoft::WRL::AsyncBase::GetOnComplete
- async/Microsoft::WRL::AsyncBase::GetOnProgress
- async/Microsoft::WRL::AsyncBase::OnCancel
- async/Microsoft::WRL::AsyncBase::OnClose
- async/Microsoft::WRL::AsyncBase::OnStart
- async/Microsoft::WRL::AsyncBase::put_Id
- async/Microsoft::WRL::AsyncBase::PutOnComplete
- async/Microsoft::WRL::AsyncBase::PutOnProgress
- async/Microsoft::WRL::AsyncBase::TryTransitionToCompleted
- async/Microsoft::WRL::AsyncBase::TryTransitionToError
helpviewer_keywords:
- Microsoft::WRL::AsyncBase class
- Microsoft::WRL::AsyncBase::AsyncBase, constructor
- Microsoft::WRL::AsyncBase::Cancel method
- Microsoft::WRL::AsyncBase::CheckValidStateForDelegateCall method
- Microsoft::WRL::AsyncBase::CheckValidStateForResultsCall method
- Microsoft::WRL::AsyncBase::Close method
- Microsoft::WRL::AsyncBase::ContinueAsyncOperation method
- Microsoft::WRL::AsyncBase::CurrentStatus method
- Microsoft::WRL::AsyncBase::ErrorCode method
- Microsoft::WRL::AsyncBase::FireCompletion method
- Microsoft::WRL::AsyncBase::FireProgress method
- Microsoft::WRL::AsyncBase::get_ErrorCode method
- Microsoft::WRL::AsyncBase::get_Id method
- Microsoft::WRL::AsyncBase::get_Status method
- Microsoft::WRL::AsyncBase::GetOnComplete method
- Microsoft::WRL::AsyncBase::GetOnProgress method
- Microsoft::WRL::AsyncBase::OnCancel method
- Microsoft::WRL::AsyncBase::OnClose method
- Microsoft::WRL::AsyncBase::OnStart method
- Microsoft::WRL::AsyncBase::put_Id method
- Microsoft::WRL::AsyncBase::PutOnComplete method
- Microsoft::WRL::AsyncBase::PutOnProgress method
- Microsoft::WRL::AsyncBase::TryTransitionToCompleted method
- Microsoft::WRL::AsyncBase::TryTransitionToError method
ms.assetid: 64259b9b-f427-4ffd-a611-e7a2f82362b2
ms.openlocfilehash: 0254aa4dc243eeffa43850c437a833a6530c01e2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371867"
---
# <a name="asyncbase-class"></a>AsyncBase Sınıfı

Windows Runtime asynchronous durum makinesini uygular.

## <a name="syntax"></a>Sözdizimi

```cpp
template <
    typename TComplete,
    typename TProgress = Details::Nil,
    AsyncResultType resultType = SingleResult
>
class AsyncBase : public AsyncBase<TComplete, Details::Nil, resultType>;

template <typename TComplete, AsyncResultType resultType>
class AsyncBase<TComplete, Details::Nil, resultType> :
    public Microsoft::WRL::Implements<IAsyncInfo>;
```

### <a name="parameters"></a>Parametreler

*Tam Tamamlama*<br/>
Bir eşzamanlı işlem tamamlandığında çağrılan bir olay işleyicisi.

*Tprogress*<br/>
Çalışan bir eşzamanlı işlem işleminde adı verilen bir olay işleyicisi, işlemin geçerli ilerlemesini bildirir.

*resultType*<br/>
[AsyncResultType](asyncresulttype-enumeration.md) numaralandırma değerlerinden biri. Varsayılan olarak, `SingleResult`.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                               | Açıklama
---------------------------------- | -------------------------------------------------
[AsyncBase::AsyncBase](#asyncbase) | `AsyncBase` sınıfının örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                         | Açıklama
-------------------------------------------- | -------------------------------------------------------------------------------------
[AsyncBase::İptal et](#cancel)                 | Eşzamanlı işlemi iptal eder.
[AsyncBase::Kapat](#close)                   | Eşzamanlı işlemi kapatır.
[AsyncBase::FireCompletion](#firecompletion) | Tamamlama olay işleyicisini çağırır veya iç ilerleme temsilcisini sıfırlar.
[AsyncBase::FireProgress](#fireprogress)     | Geçerli ilerleme olay işleyicisini çağırır.
[AsyncBase::get_ErrorCode](#get-errorcode)   | Geçerli eşzamanlı işlemin hata kodunu alır.
[AsyncBase::get_Id](#get-id)                 | Eşzamanlı işlemin tutamacını alır.
[AsyncBase::get_Status](#get-status)         | Eşzamanlı işlemin durumunu gösteren bir değer alır.
[AsyncBase::GetOnComplete](#getoncomplete)   | Geçerli tamamlama olay işleyicisinin adresini belirtilen değişkene kopyalar.
[AsyncBase::GetOnProgress](#getonprogress)   | Geçerli ilerleme olay işleyicisinin adresini belirtilen değişkene kopyalar.
[AsyncBase::put_Id](#put-id)                 | Eşzamanlı işlemin tutamacını ayarlar.
[AsyncBase::PutOnComplete](#putoncomplete)   | Tamamlanma olayı işleyicisinin adresini belirtilen değere ayarlar.
[AsyncBase::PutOnProgress](#putonprogress)   | İlerleme olay işleyicisinin adresini belirtilen değere ayarlar.

### <a name="protected-methods"></a>Korumalı Yöntemler

Adı                                                                         | Açıklama
---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[AsyncBase::CheckValidStateForDelege Çağrısı](#checkvalidstatefordelegatecall) | Geçerli asenkron durumda temsilci özelliklerinin değiştirilip değiştirilemeyeceğini sınama.
[AsyncBase::CheckValidStateForResultsCall](#checkvalidstateforresultscall)   | Eşzamanlı işlemin sonuçlarının geçerli asenkron durumda toplanıp toplanamayacağını test edin.
[AsyncBase::ContinueAsyncİşlem](#continueasyncoperation)                 | Eşzamanlı işlemin işleme devam edip etmeyeceğini veya durdurulması nı belirler.
[AsyncBase::Geçerli Durum](#currentstatus)                                   | Geçerli eşzamanlı işlemin durumunu alır.
[AsyncBase::Hata Kodu](#errorcode)                                           | Geçerli eşzamanlı işlemin hata kodunu alır.
[AsyncBase::OnCancel](#oncancel)                                             | Türemiş bir sınıfta geçersiz kılındığında, eşzamanlı işlemi iptal eder.
[AsyncBase::OnClose](#onclose)                                               | Türetilmiş bir sınıfta geçersiz kılındığında, eşzamanlı bir işlemi kapatır.
[AsyncBase::Başlangıç](#onstart)                                               | Türemiş bir sınıfta geçersiz kılındığında, eşzamanlı bir işlem başlar.
[AsyncBase::Başlat](#start)                                                   | Eşzamanlı işlemi başlatır.
[AsyncBase::TryTransitionToCompleted](#trytransitiontocompleted)             | Geçerli eşzamanlı işlemin tamamlanıp tamamlanmadığını gösterir.
[AsyncBase::TryTransitionToError](#trytransitiontoerror)                     | Belirtilen hata kodunun iç hata durumunu değiştirip değiştiremeyeceğini gösterir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`AsyncBase`

`AsyncBase`

## <a name="requirements"></a>Gereksinimler

**Üstbilgi:** async.h

**Ad alanı:** Microsoft::WRL

## <a name="asyncbaseasyncbase"></a><a name="asyncbase"></a>AsyncBase::AsyncBase

`AsyncBase` sınıfının örneğini başlatır.

```cpp
AsyncBase();
```

## <a name="asyncbasecancel"></a><a name="cancel"></a>AsyncBase::İptal et

Eşzamanlı işlemi iptal eder.

```cpp
STDMETHOD(
   Cancel
)(void);
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan olarak, her zaman S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

`Cancel()`varsayılan bir uygulamadır `IAsyncInfo::Cancel`ve gerçek bir iş yapmaz. Bir eşzamanlı işlemi gerçekten iptal etmek `OnCancel()` için, saf sanal yöntemi geçersiz kılın.

## <a name="asyncbasecheckvalidstatefordelegatecall"></a><a name="checkvalidstatefordelegatecall"></a>AsyncBase::CheckValidStateForDelege Çağrısı

Geçerli asenkron durumda temsilci özelliklerinin değiştirilip değiştirilemeyeceğini sınama.

```cpp
inline HRESULT CheckValidStateForDelegateCall();
```

### <a name="return-value"></a>Dönüş Değeri

temsilci özellikleri değiştirilebilirse S_OK; aksi takdirde, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbasecheckvalidstateforresultscall"></a><a name="checkvalidstateforresultscall"></a>AsyncBase::CheckValidStateForResultsCall

Eşzamanlı işlemin sonuçlarının geçerli asenkron durumda toplanıp toplanamayacağını test edin.

```cpp
inline HRESULT CheckValidStateForResultsCall();
```

### <a name="return-value"></a>Dönüş Değeri

sonuçların toplanıp toplanmayabileceğini S_OK; aksi takdirde, E_ILLEGAL_METHOD_CALLE_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseclose"></a><a name="close"></a>AsyncBase::Kapat

Eşzamanlı işlemi kapatır.

```cpp
STDMETHOD(
   Close
)(void) override;
```

### <a name="return-value"></a>Dönüş Değeri

S_OK işlem kapanırsa veya zaten kapalıysa; aksi takdirde, E_ILLEGAL_STATE_CHANGE.

### <a name="remarks"></a>Açıklamalar

`Close()`varsayılan bir uygulamadır `IAsyncInfo::Close`ve gerçek bir iş yapmaz. Bir eşzamanlı işlemi gerçekten kapatmak `OnClose()` için, saf sanal yöntemi geçersiz kılın.

## <a name="asyncbasecontinueasyncoperation"></a><a name="continueasyncoperation"></a>AsyncBase::ContinueAsyncİşlem

Eşzamanlı işlemin işleme devam edip etmeyeceğini veya durdurulması nı belirler.

```cpp
inline bool ContinueAsyncOperation();
```

### <a name="return-value"></a>Dönüş Değeri

eşzamanlı işlemin geçerli durumu *başlatılırsa* **doğru,** bu da işlemin devam etmesi gerektiği anlamına gelir. Aksi takdirde, **yanlış**, hangi işlem durdurmak gerektiği anlamına gelir.

## <a name="asyncbasecurrentstatus"></a><a name="currentstatus"></a>AsyncBase::Geçerli Durum

Geçerli eşzamanlı işlemin durumunu alır.

```cpp
inline void CurrentStatus(
   Details::AsyncStatusInternal *status
);
```

### <a name="parameters"></a>Parametreler

*Durum*<br/>
Bu işlemin geçerli durumu depoladığı konum.

### <a name="remarks"></a>Açıklamalar

Bu işlem iş parçacığı için güvenlidir.

## <a name="asyncbaseerrorcode"></a><a name="errorcode"></a>AsyncBase::Hata Kodu

Geçerli eşzamanlı işlemin hata kodunu alır.

```cpp
inline void ErrorCode(
   HRESULT *error
);
```

### <a name="parameters"></a>Parametreler

*error*<br/>
Bu işlemin geçerli hata kodunu depoladığı konum.

### <a name="remarks"></a>Açıklamalar

Bu işlem iş parçacığı için güvenlidir.

## <a name="asyncbasefirecompletion"></a><a name="firecompletion"></a>AsyncBase::FireCompletion

Tamamlama olay işleyicisini çağırır veya iç ilerleme temsilcisini sıfırlar.

```cpp
void FireCompletion(
   void
) override;

virtual void FireCompletion();
```

### <a name="remarks"></a>Açıklamalar

İlk sürümü `FireCompletion()` iç ilerleme temsilcisi değişkenini sıfırlar. Eşsenkronize işlem tamamlandığında ikinci sürüm tamamlanma olay işleyicisi çağırır.

## <a name="asyncbasefireprogress"></a><a name="fireprogress"></a>AsyncBase::FireProgress

Geçerli ilerleme olay işleyicisini çağırır.

```cpp
void FireProgress(
   const typename ProgressTraits::Arg2Type arg
);
```

### <a name="parameters"></a>Parametreler

*Arg*<br/>
Çağırmak için olay işleyicisi yöntemi.

### <a name="remarks"></a>Açıklamalar

`ProgressTraits`[ArgTraitsHelper Yapısı'ndan](argtraitshelper-structure.md)türetilmiştir.

## <a name="asyncbaseget_errorcode"></a><a name="get-errorcode"></a>AsyncBase::get_ErrorCode

Geçerli eşzamanlı işlemin hata kodunu alır.

```cpp
STDMETHOD(
   get_ErrorCode
)(HRESULT* errorCode) override;
```

### <a name="parameters"></a>Parametreler

*hataKodu*<br/>
Geçerli hata kodunun depolandığı konum.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, geçerli eşzamanlı işlem kapatılırsa E_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseget_id"></a><a name="get-id"></a>AsyncBase::get_Id

Eşzamanlı işlemin tutamacını alır.

```cpp
STDMETHOD(
   get_Id
)(unsigned int *id) override;
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
Tanıtıcının depolanacak olduğu yer.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, E_ILLEGAL_METHOD_CALL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem `IAsyncInfo::get_Id`uygular.

## <a name="asyncbaseget_status"></a><a name="get-status"></a>AsyncBase::get_Status

Eşzamanlı işlemin durumunu gösteren bir değer alır.

```cpp
STDMETHOD(
   get_Status
)(AsyncStatus *status) override;
```

### <a name="parameters"></a>Parametreler

*Durum*<br/>
Durumun depolanacak olduğu yer. Daha fazla bilgi `Windows::Foundation::AsyncStatus` için numaralandırmaya bakın.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, E_ILLEGAL_METHOD_CALL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem `IAsyncInfo::get_Status`uygular.

## <a name="asyncbasegetoncomplete"></a><a name="getoncomplete"></a>AsyncBase::GetOnComplete

Geçerli tamamlama olay işleyicisinin adresini belirtilen değişkene kopyalar.

```cpp
STDMETHOD(
   GetOnComplete
)(TComplete** completeHandler);
```

### <a name="parameters"></a>Parametreler

*completeHandler*<br/>
Geçerli tamamlama olay işleyicisinin adresinin depolandığı konum.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbasegetonprogress"></a><a name="getonprogress"></a>AsyncBase::GetOnProgress

Geçerli ilerleme olay işleyicisinin adresini belirtilen değişkene kopyalar.

```cpp
STDMETHOD(
   GetOnProgress
)(TProgress** progressHandler);
```

### <a name="parameters"></a>Parametreler

*ilerlemeHandler*<br/>
Geçerli ilerleme olay işleyicisinin adresinin depolandığı konum.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseoncancel"></a><a name="oncancel"></a>AsyncBase::OnCancel

Türemiş bir sınıfta geçersiz kılındığında, eşzamanlı işlemi iptal eder.

```cpp
virtual void OnCancel(
   void
) = 0;
```

## <a name="asyncbaseonclose"></a><a name="onclose"></a>AsyncBase::OnClose

Türetilmiş bir sınıfta geçersiz kılındığında, eşzamanlı bir işlemi kapatır.

```cpp
virtual void OnClose(
   void
) = 0;
```

## <a name="asyncbaseonstart"></a><a name="onstart"></a>AsyncBase::Başlangıç

Türemiş bir sınıfta geçersiz kılındığında, eşzamanlı bir işlem başlar.

```cpp
virtual HRESULT OnStart(
   void
) = 0;
```

## <a name="asyncbaseput_id"></a><a name="put-id"></a>AsyncBase::put_Id

Eşzamanlı işlemin tutamacını ayarlar.

```cpp
STDMETHOD(
   put_Id
)(const unsigned int id);
```

### <a name="parameters"></a>Parametreler

*Kimliği*<br/>
Sıfır olmayan bir kulp.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, E_INVALIDARG veya E_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseputoncomplete"></a><a name="putoncomplete"></a>AsyncBase::PutOnComplete

Tamamlanma olayı işleyicisinin adresini belirtilen değere ayarlar.

```cpp
STDMETHOD(
   PutOnComplete
)(TComplete* completeHandler);
```

### <a name="parameters"></a>Parametreler

*completeHandler*<br/>
Tamamlama olay işleyicisinin ayarlandığı adres.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseputonprogress"></a><a name="putonprogress"></a>AsyncBase::PutOnProgress

İlerleme olay işleyicisinin adresini belirtilen değere ayarlar.

```cpp
STDMETHOD(
   PutOnProgress
)(TProgress* progressHandler);
```

### <a name="parameters"></a>Parametreler

*ilerlemeHandler*<br/>
İlerleme olayı işleyicisinin ayarlandığı adres.

### <a name="return-value"></a>Dönüş Değeri

S_OK başarılı olursa; aksi takdirde, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbasestart"></a><a name="start"></a>AsyncBase::Başlat

Eşzamanlı işlemi başlatır.

```cpp
STDMETHOD(
   Start
)(void);
```

### <a name="return-value"></a>Dönüş Değeri

S_OK başlatılırsa veya zaten başlatılırsa; aksi takdirde, E_ILLEGAL_STATE_CHANGE.

### <a name="remarks"></a>Açıklamalar

`Start()`async, arayanın geri dönmeden önce "sıcak başlangıç" işlemleri yaptığı için dışarıdan görülemeyen korumalı bir yöntemdir.

## <a name="asyncbasetrytransitiontocompleted"></a><a name="trytransitiontocompleted"></a>AsyncBase::TryTransitionToCompleted

Geçerli eşzamanlı işlemin tamamlanıp tamamlanmadığını gösterir.

```cpp
bool TryTransitionToCompleted(
   void
);
```

### <a name="return-value"></a>Dönüş Değeri

eşzamanlı işlem tamamlanmışsa **doğrudur;** aksi takdirde, **yanlış**.

## <a name="asyncbasetrytransitiontoerror"></a><a name="trytransitiontoerror"></a>AsyncBase::TryTransitionToError

Belirtilen hata kodunun iç hata durumunu değiştirip değiştiremeyeceğini gösterir.

```cpp
bool TryTransitionToError(
   const HRESULT error
);
```

### <a name="parameters"></a>Parametreler

*error*<br/>
Bir hata HRESULT.

### <a name="return-value"></a>Dönüş Değeri

iç hata durumu değiştirildiyse **doğru;** aksi takdirde, **yanlış**.

### <a name="remarks"></a>Açıklamalar

Bu işlem, yalnızca hata durumu zaten S_OK ayarlanmışsa hata durumunu değiştirir. Hata durumu zaten hata ysa, iptal edildiyse, tamamlansa veya kapatılırsa, bu işlemin hiçbir etkisi yoktur.
