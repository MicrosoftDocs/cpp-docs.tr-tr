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
ms.openlocfilehash: 09819c9e8dd924581ce8cd67233d273f7e8d62ca
ms.sourcegitcommit: 8e285a766523e653aeeb34d412dc6f615ef7b17b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/21/2020
ms.locfileid: "80079905"
---
# <a name="asyncbase-class"></a>AsyncBase Sınıfı

Windows Çalışma Zamanı zaman uyumsuz durum makinesini uygular.

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

*Ttamam*<br/>
Zaman uyumsuz bir işlem tamamlandığında çağrılan bir olay işleyicisi.

*TProgress*<br/>
Çalışan bir zaman uyumsuz işlem, işlemin geçerli ilerlemesini raporladığında çağrılan bir olay işleyicisi.

*'ı*<br/>
[AsyncResultType](asyncresulttype-enumeration.md) numaralandırma değerlerinden biri. Varsayılan olarak, `SingleResult`.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Adı                               | Açıklama
---------------------------------- | -------------------------------------------------
[AsyncBase:: AsyncBase](#asyncbase) | `AsyncBase` sınıfının örneğini başlatır.

### <a name="public-methods"></a>Ortak Yöntemler

Adı                                         | Açıklama
-------------------------------------------- | -------------------------------------------------------------------------------------
[AsyncBase:: Cancel](#cancel)                 | Zaman uyumsuz bir işlemi iptal eder.
[AsyncBase:: Close](#close)                   | Zaman uyumsuz işlemi kapatır.
[AsyncBase:: FireCompletion](#firecompletion) | Tamamlanma olayı işleyicisini çağırır veya iç ilerleme temsilcisini sıfırlar.
[AsyncBase:: FireProgress](#fireprogress)     | Geçerli ilerleme olayı işleyicisini çağırır.
[AsyncBase:: get_ErrorCode](#get-errorcode)   | Geçerli zaman uyumsuz işlem için hata kodunu alır.
[AsyncBase:: get_Id](#get-id)                 | Zaman uyumsuz işlemin tanıtıcısını alır.
[AsyncBase:: get_Status](#get-status)         | Zaman uyumsuz işlemin durumunu gösteren bir değer alır.
[AsyncBase:: Getontamamlanmıştır](#getoncomplete)   | Geçerli tamamlanma olayı işleyicisinin adresini belirtilen değişkene kopyalar.
[AsyncBase:: GetOnProgress](#getonprogress)   | Geçerli ilerleme olayı işleyicisinin adresini belirtilen değişkene kopyalar.
[AsyncBase::p ut_Id](#put-id)                 | Zaman uyumsuz işlemin tanıtıcısını ayarlar.
[AsyncBase::P Uıtontamamlanmıştır](#putoncomplete)   | Tamamlanma olayı işleyicisinin adresini belirtilen değere ayarlar.
[AsyncBase::P Uıtonprogress](#putonprogress)   | İlerleme olayı işleyicisinin adresini belirtilen değere ayarlar.

### <a name="protected-methods"></a>Korumalı Yöntemler

Adı                                                                         | Açıklama
---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[AsyncBase:: CheckValidStateForDelegateCall](#checkvalidstatefordelegatecall) | Temsilci özelliklerinin geçerli zaman uyumsuz durumda değiştirilip değiştirilemeyeceğini sınar.
[AsyncBase:: CheckValidStateForResultsCall](#checkvalidstateforresultscall)   | Zaman uyumsuz bir işlemin sonuçlarının geçerli zaman uyumsuz durumda toplanıp toplanamayacağını sınar.
[AsyncBase:: ContinueAsyncOperation](#continueasyncoperation)                 | Zaman uyumsuz işlemin işleme devam edip etmediğini mi yoksa durdurmak mı gerektiğini belirler.
[AsyncBase:: CurrentStatus](#currentstatus)                                   | Geçerli zaman uyumsuz işlemin durumunu alır.
[AsyncBase:: ErrorCode](#errorcode)                                           | Geçerli zaman uyumsuz işlem için hata kodunu alır.
[AsyncBase:: OnCancel](#oncancel)                                             | Türetilmiş bir sınıfta geçersiz kılınırsa, zaman uyumsuz bir işlemi iptal eder.
[AsyncBase:: OnClose](#onclose)                                               | Türetilmiş bir sınıfta geçersiz kılınırsa, zaman uyumsuz bir işlemi kapatır.
[AsyncBase:: OnStart](#onstart)                                               | Türetilmiş bir sınıfta geçersiz kılınırsa, zaman uyumsuz bir işlem başlatır.
[AsyncBase:: Start](#start)                                                   | Zaman uyumsuz işlemi başlatır.
[AsyncBase:: Trygeçişli Tiontocompleted](#trytransitiontocompleted)             | Geçerli zaman uyumsuz işlemin tamamlanıp tamamlanmadığını belirtir.
[AsyncBase:: Trygeçişli Tiontoerror](#trytransitiontoerror)                     | Belirtilen hata kodunun iç hata durumunu değiştiremeyeceğini gösterir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`AsyncBase`

`AsyncBase`

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** Async. h

**Ad alanı:** Microsoft:: WRL

## <a name="asyncbaseasyncbase"></a><a name="asyncbase"></a>AsyncBase:: AsyncBase

`AsyncBase` sınıfının örneğini başlatır.

```cpp
AsyncBase();
```

## <a name="asyncbasecancel"></a><a name="cancel"></a>AsyncBase:: Cancel

Zaman uyumsuz bir işlemi iptal eder.

```cpp
STDMETHOD(
   Cancel
)(void);
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan olarak her zaman S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

`Cancel()` varsayılan bir `IAsyncInfo::Cancel`uygulamasıdır ve gerçek çalışma yapmaz. Gerçekten zaman uyumsuz bir işlemi iptal etmek için `OnCancel()` saf sanal yöntemini geçersiz kılın.

## <a name="asyncbasecheckvalidstatefordelegatecall"></a><a name="checkvalidstatefordelegatecall"></a>AsyncBase:: CheckValidStateForDelegateCall

Temsilci özelliklerinin geçerli zaman uyumsuz durumda değiştirilip değiştirilemeyeceğini sınar.

```cpp
inline HRESULT CheckValidStateForDelegateCall();
```

### <a name="return-value"></a>Dönüş Değeri

Temsilci özellikleri değiştirilemiyorsa, S_OK. Aksi takdirde, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbasecheckvalidstateforresultscall"></a><a name="checkvalidstateforresultscall"></a>AsyncBase:: CheckValidStateForResultsCall

Zaman uyumsuz bir işlemin sonuçlarının geçerli zaman uyumsuz durumda toplanıp toplanamayacağını sınar.

```cpp
inline HRESULT CheckValidStateForResultsCall();
```

### <a name="return-value"></a>Dönüş Değeri

Sonuçların toplanabilmesi S_OK; Aksi takdirde, E_ILLEGAL_METHOD_CALLE_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseclose"></a><a name="close"></a>AsyncBase:: Close

Zaman uyumsuz işlemi kapatır.

```cpp
STDMETHOD(
   Close
)(void) override;
```

### <a name="return-value"></a>Dönüş Değeri

İşlem kapatılırsa veya zaten kapalıysa S_OK; Aksi takdirde, E_ILLEGAL_STATE_CHANGE.

### <a name="remarks"></a>Açıklamalar

`Close()` varsayılan bir `IAsyncInfo::Close`uygulamasıdır ve gerçek çalışma yapmaz. Bir zaman uyumsuz işlemi gerçekten kapatmak için `OnClose()` saf sanal metodunu geçersiz kılın.

## <a name="asyncbasecontinueasyncoperation"></a><a name="continueasyncoperation"></a>AsyncBase:: ContinueAsyncOperation

Zaman uyumsuz işlemin işleme devam edip etmediğini mi yoksa durdurmak mı gerektiğini belirler.

```cpp
inline bool ContinueAsyncOperation();
```

### <a name="return-value"></a>Dönüş Değeri

zaman uyumsuz işlemin geçerli durumu *başlatılmışsa* **true** , yani işlemin devam etmesi gerekir. Aksi takdirde, **yanlış**, işlemin durdurmayacağı anlamına gelir.

## <a name="asyncbasecurrentstatus"></a><a name="currentstatus"></a>AsyncBase:: CurrentStatus

Geçerli zaman uyumsuz işlemin durumunu alır.

```cpp
inline void CurrentStatus(
   Details::AsyncStatusInternal *status
);
```

### <a name="parameters"></a>Parametreler

*durumlarına*<br/>
Bu işlemin geçerli durumu depoladığı konum.

### <a name="remarks"></a>Açıklamalar

Bu işlem iş parçacığı açısından güvenlidir.

## <a name="asyncbaseerrorcode"></a><a name="errorcode"></a>AsyncBase:: ErrorCode

Geçerli zaman uyumsuz işlem için hata kodunu alır.

```cpp
inline void ErrorCode(
   HRESULT *error
);
```

### <a name="parameters"></a>Parametreler

*hatayla*<br/>
Bu işlemin geçerli hata kodunu depoladığı konum.

### <a name="remarks"></a>Açıklamalar

Bu işlem iş parçacığı açısından güvenlidir.

## <a name="asyncbasefirecompletion"></a><a name="firecompletion"></a>AsyncBase:: FireCompletion

Tamamlanma olayı işleyicisini çağırır veya iç ilerleme temsilcisini sıfırlar.

```cpp
void FireCompletion(
   void
) override;

virtual void FireCompletion();
```

### <a name="remarks"></a>Açıklamalar

`FireCompletion()` ilk sürümü, iç ilerleme temsilcisi değişkenini sıfırlar. İkinci sürüm, zaman uyumsuz işlem tamamlandıktan sonra tamamlanma olayı işleyicisini çağırır.

## <a name="asyncbasefireprogress"></a><a name="fireprogress"></a>AsyncBase:: FireProgress

Geçerli ilerleme olayı işleyicisini çağırır.

```cpp
void FireProgress(
   const typename ProgressTraits::Arg2Type arg
);
```

### <a name="parameters"></a>Parametreler

*değişkeni*<br/>
Çağrılacak olay işleyicisi yöntemi.

### <a name="remarks"></a>Açıklamalar

`ProgressTraits`, [Yapı başına Argtraitshelfrom](argtraitshelper-structure.md)öğesinden türetilir.

## <a name="asyncbaseget_errorcode"></a><a name="get-errorcode"></a>AsyncBase:: get_ErrorCode

Geçerli zaman uyumsuz işlem için hata kodunu alır.

```cpp
STDMETHOD(
   get_ErrorCode
)(HRESULT* errorCode) override;
```

### <a name="parameters"></a>Parametreler

*Raporladı*<br/>
Geçerli hata kodunun depolandığı konum.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, geçerli zaman uyumsuz işlem kapalıysa E_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseget_id"></a><a name="get-id"></a>AsyncBase:: get_Id

Zaman uyumsuz işlemin tanıtıcısını alır.

```cpp
STDMETHOD(
   get_Id
)(unsigned int *id) override;
```

### <a name="parameters"></a>Parametreler

*id*<br/>
Tanıtıcının depolanacağı konum.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, E_ILLEGAL_METHOD_CALL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem `IAsyncInfo::get_Id`uygular.

## <a name="asyncbaseget_status"></a><a name="get-status"></a>AsyncBase:: get_Status

Zaman uyumsuz işlemin durumunu gösteren bir değer alır.

```cpp
STDMETHOD(
   get_Status
)(AsyncStatus *status) override;
```

### <a name="parameters"></a>Parametreler

*durumlarına*<br/>
Durumun depolanacağı konum. Daha fazla bilgi için bkz. `Windows::Foundation::AsyncStatus` numaralandırması.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, E_ILLEGAL_METHOD_CALL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem `IAsyncInfo::get_Status`uygular.

## <a name="asyncbasegetoncomplete"></a><a name="getoncomplete"></a>AsyncBase:: Getontamamlanmıştır

Geçerli tamamlanma olayı işleyicisinin adresini belirtilen değişkene kopyalar.

```cpp
STDMETHOD(
   GetOnComplete
)(TComplete** completeHandler);
```

### <a name="parameters"></a>Parametreler

*completeHandler*<br/>
Geçerli tamamlanma olayı işleyicisinin adresinin depolandığı konum.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbasegetonprogress"></a><a name="getonprogress"></a>AsyncBase:: GetOnProgress

Geçerli ilerleme olayı işleyicisinin adresini belirtilen değişkene kopyalar.

```cpp
STDMETHOD(
   GetOnProgress
)(TProgress** progressHandler);
```

### <a name="parameters"></a>Parametreler

*progressHandler*<br/>
Geçerli ilerleme olayı işleyicisinin adresinin depolandığı konum.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseoncancel"></a><a name="oncancel"></a>AsyncBase:: OnCancel

Türetilmiş bir sınıfta geçersiz kılınırsa, zaman uyumsuz bir işlemi iptal eder.

```cpp
virtual void OnCancel(
   void
) = 0;
```

## <a name="asyncbaseonclose"></a><a name="onclose"></a>AsyncBase:: OnClose

Türetilmiş bir sınıfta geçersiz kılınırsa, zaman uyumsuz bir işlemi kapatır.

```cpp
virtual void OnClose(
   void
) = 0;
```

## <a name="asyncbaseonstart"></a><a name="onstart"></a>AsyncBase:: OnStart

Türetilmiş bir sınıfta geçersiz kılınırsa, zaman uyumsuz bir işlem başlatır.

```cpp
virtual HRESULT OnStart(
   void
) = 0;
```

## <a name="asyncbaseput_id"></a><a name="put-id"></a>AsyncBase::p ut_Id

Zaman uyumsuz işlemin tanıtıcısını ayarlar.

```cpp
STDMETHOD(
   put_Id
)(const unsigned int id);
```

### <a name="parameters"></a>Parametreler

*id*<br/>
Sıfır dışında bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, E_INVALIDARG veya E_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseputoncomplete"></a><a name="putoncomplete"></a>AsyncBase::P Uıtontamamlanmıştır

Tamamlanma olayı işleyicisinin adresini belirtilen değere ayarlar.

```cpp
STDMETHOD(
   PutOnComplete
)(TComplete* completeHandler);
```

### <a name="parameters"></a>Parametreler

*completeHandler*<br/>
Tamamlanma olayı işleyicisinin ayarlandığı adres.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbaseputonprogress"></a><a name="putonprogress"></a>AsyncBase::P Uıtonprogress

İlerleme olayı işleyicisinin adresini belirtilen değere ayarlar.

```cpp
STDMETHOD(
   PutOnProgress
)(TProgress* progressHandler);
```

### <a name="parameters"></a>Parametreler

*progressHandler*<br/>
İlerleme olayı işleyicisinin ayarlandığı adres.

### <a name="return-value"></a>Dönüş Değeri

Başarılı olursa S_OK; Aksi takdirde, E_ILLEGAL_METHOD_CALL.

## <a name="asyncbasestart"></a><a name="start"></a>AsyncBase:: Start

Zaman uyumsuz işlemi başlatır.

```cpp
STDMETHOD(
   Start
)(void);
```

### <a name="return-value"></a>Dönüş Değeri

İşlem başlarsa veya zaten başlatılmış S_OK; Aksi takdirde, E_ILLEGAL_STATE_CHANGE.

### <a name="remarks"></a>Açıklamalar

`Start()`, çağrı yapana dönmeden önce zaman uyumsuz işlemler "etkin başlatma" nedeniyle dışarıdan görünmeyen korumalı bir yöntemdir.

## <a name="asyncbasetrytransitiontocompleted"></a><a name="trytransitiontocompleted"></a>AsyncBase:: Trygeçişli Tiontocompleted

Geçerli zaman uyumsuz işlemin tamamlanıp tamamlanmadığını belirtir.

```cpp
bool TryTransitionToCompleted(
   void
);
```

### <a name="return-value"></a>Dönüş Değeri

zaman uyumsuz işlem tamamlanırsa **doğru** ; Aksi takdirde, **false**.

## <a name="asyncbasetrytransitiontoerror"></a><a name="trytransitiontoerror"></a>AsyncBase:: Trygeçişli Tiontoerror

Belirtilen hata kodunun iç hata durumunu değiştiremeyeceğini gösterir.

```cpp
bool TryTransitionToError(
   const HRESULT error
);
```

### <a name="parameters"></a>Parametreler

*hatayla*<br/>
Bir HRESULT hatası.

### <a name="return-value"></a>Dönüş Değeri

iç hata durumu değiştiyse **doğru** ; Aksi takdirde, **false**.

### <a name="remarks"></a>Açıklamalar

Bu işlem yalnızca hata durumu zaten S_OK olarak ayarlandıysa hata durumunu değiştirir. Hata durumu zaten hata, iptal edildi, tamamlandı veya kapatıldı olduğunda bu işlemin etkisi yoktur.
