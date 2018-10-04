---
title: AsyncBase sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
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
- async/Microsoft::WRL::AsyncBase::Start
- async/Microsoft::WRL::AsyncBase::TryTransitionToCompleted
- async/Microsoft::WRL::AsyncBase::TryTransitionToError
dev_langs:
- C++
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
- Microsoft::WRL::AsyncBase::Start method
- Microsoft::WRL::AsyncBase::TryTransitionToCompleted method
- Microsoft::WRL::AsyncBase::TryTransitionToError method
ms.assetid: 64259b9b-f427-4ffd-a611-e7a2f82362b2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6538d06c291bccc8764403b26f5c8d88f4afd781
ms.sourcegitcommit: 955ef0f9d966e7c9c65e040f1e28fa83abe102a5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/04/2018
ms.locfileid: "48788805"
---
# <a name="asyncbase-class"></a>AsyncBase Sınıfı

Windows çalışma zamanı zaman uyumsuz Durum makinesi uygular.

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

*TComplete*<br/>
Bir zaman uyumsuz işlem tamamlandığında çağrılan bir olay işleyicisi.

*TProgress*<br/>
Bir çalıştırma zaman uyumsuz işlem geçerli işlemin ilerlemesini bildirdiğinde çağrılan bir olay işleyicisi.

*resulttype'ı*<br/>
Aşağıdakilerden birini [AsyncResultType](../windows/asyncresulttype-enumeration.md) sabit listesi değerleri. Varsayılan olarak, `SingleResult`.

## <a name="members"></a>Üyeler

### <a name="public-constructors"></a>Ortak Oluşturucular

Ad                               | Açıklama
---------------------------------- | -------------------------------------------------
[AsyncBase::AsyncBase](#asyncbase) | Bir örneğini başlatır `AsyncBase` sınıfı.

### <a name="public-methods"></a>Ortak Yöntemler

Ad                                         | Açıklama
-------------------------------------------- | -------------------------------------------------------------------------------------
[AsyncBase::Cancel](#cancel)                 | Zaman uyumsuz bir işlem iptal eder.
[AsyncBase::Close](#close)                   | Zaman uyumsuz işlemi kapatır.
[AsyncBase::FireCompletion](#firecompletion) | Tamamlanma olayı işleyicisini çağırır veya iç ilerleme temsilci sıfırlar.
[AsyncBase::FireProgress](#fireprogress)     | Geçerli ilerleme olay işleyicisini çağırır.
[AsyncBase::get_ErrorCode](#get-errorcode)   | Geçerli zaman uyumsuz işlem hata kodunu alır.
[Asyncbase::get_ıd](#get-id)                 | Zaman uyumsuz işlem tanıtıcısını alır.
[AsyncBase::get_Status](#get-status)         | Zaman uyumsuz işlemin durumunu gösteren bir değer alır.
[AsyncBase::GetOnComplete](#getoncomplete)   | Adres geçerli tamamlama olay işleyicisinin belirtilen değişkenine kopyalar.
[AsyncBase::GetOnProgress](#getonprogress)   | Adres geçerli ilerleme olay işleyicisinin belirtilen değişkenine kopyalar.
[Asyncbase::put_ıd](#put-id)                 | Zaman uyumsuz işlem tanıtıcısı ayarlar.
[AsyncBase::PutOnComplete](#putoncomplete)   | Tamamlama olay işleyicisinin adresi belirtilen değere ayarlar.
[AsyncBase::PutOnProgress](#putonprogress)   | Devam eden olay işleyicisinin adresi belirtilen değere ayarlar.
[AsyncBase::Start](#start)                   | Zaman uyumsuz işlemi başlatır.

### <a name="protected-methods"></a>Korumalı Yöntemler

Ad                                                                         | Açıklama
---------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------
[AsyncBase::CheckValidStateForDelegateCall](#checkvalidstatefordelegatecall) | Temsilci özellikleri geçerli zaman uyumsuz durumunda değiştirilebilir olup olmadığını sınar.
[AsyncBase::CheckValidStateForResultsCall](#checkvalidstateforresultscall)   | Geçerli zaman uyumsuz durumda zaman uyumsuz bir işlemin sonuçları toplanabilir olup olmadığını sınar.
[AsyncBase::ContinueAsyncOperation](#continueasyncoperation)                 | Zaman uyumsuz işlem işlemeye devam etmesi gerektiğinin veya durdurmak belirler.
[AsyncBase::CurrentStatus](#currentstatus)                                   | Geçerli zaman uyumsuz işlemin durumunu alır.
[AsyncBase::ErrorCode](#errorcode)                                           | Geçerli zaman uyumsuz işlem hata kodunu alır.
[AsyncBase::OnCancel](#oncancel)                                             | Türetilen bir sınıfta geçersiz kılındığında, bir zaman uyumsuz işlem iptal eder.
[AsyncBase::OnClose](#onclose)                                               | Türetilen bir sınıfta geçersiz kılındığında, zaman uyumsuz bir işlem kapatır.
[AsyncBase::OnStart](#onstart)                                               | Türetilen bir sınıfta geçersiz kılındığında, zaman uyumsuz bir işlem başlatır.
[AsyncBase::TryTransitionToCompleted](#trytransitiontocompleted)             | Geçerli zaman uyumsuz işlem tamamlanıp tamamlanmadığını gösterir.
[AsyncBase::TryTransitionToError](#trytransitiontoerror)                     | Belirtilen hata kodu iç hata durumunda değiştirip değiştiremeyeceğini belirtir.

## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi

`AsyncBase`

`AsyncBase`

## <a name="requirements"></a>Gereksinimler

**Başlık:** async.h

**Namespace:** Microsoft::WRL

## <a name="asyncbase"></a>AsyncBase::AsyncBase

Bir örneğini başlatır `AsyncBase` sınıfı.

```cpp
AsyncBase();
```

## <a name="cancel"></a>AsyncBase::Cancel

Zaman uyumsuz bir işlem iptal eder.

```cpp
STDMETHOD(
   Cancel
)(void);
```

### <a name="return-value"></a>Dönüş Değeri

Varsayılan olarak, her zaman S_OK döndürür.

### <a name="remarks"></a>Açıklamalar

`Cancel()` bir varsayılan uygulamasıdır `IAsyncInfo::Cancel`, ve hiçbir asıl işi yapar. Zaman uyumsuz bir işlem gerçekten iptal etmek için geçersiz kılma `OnCancel()` saf sanal yöntemi.

## <a name="checkvalidstatefordelegatecall"></a>AsyncBase::CheckValidStateForDelegateCall

Temsilci özellikleri geçerli zaman uyumsuz durumunda değiştirilebilir olup olmadığını sınar.

```cpp
inline HRESULT CheckValidStateForDelegateCall();
```

### <a name="return-value"></a>Dönüş Değeri

Temsilci özellikleri değiştirilip değiştirilmediğini S_OK; Aksi takdirde, E_ILLEGAL_METHOD_CALL.

## <a name="checkvalidstateforresultscall"></a>AsyncBase::CheckValidStateForResultsCall

Geçerli zaman uyumsuz durumda zaman uyumsuz bir işlemin sonuçları toplanabilir olup olmadığını sınar.

```cpp
inline HRESULT CheckValidStateForResultsCall();
```

### <a name="return-value"></a>Dönüş Değeri

S_OK sonuçları toplanabilir; Aksi takdirde, E_ILLEGAL_METHOD_CALLE_ILLEGAL_METHOD_CALL.

## <a name="close"></a>AsyncBase::Close

Zaman uyumsuz işlemi kapatır.

```cpp
STDMETHOD(
   Close
)(void) override;
```

### <a name="return-value"></a>Dönüş Değeri

İşlemi kapatır veya zaten S_OK kapalı; Aksi takdirde, E_ILLEGAL_STATE_CHANGE.

### <a name="remarks"></a>Açıklamalar

`Close()` bir varsayılan uygulamasıdır `IAsyncInfo::Close`, ve hiçbir asıl işi yapar. Zaman uyumsuz bir işlem gerçekten kapatmak için geçersiz kılma `OnClose()` saf sanal yöntemi.

## <a name="continueasyncoperation"></a>AsyncBase::ContinueAsyncOperation

Zaman uyumsuz işlem işlemeye devam etmesi gerektiğinin veya durdurmak belirler.

```cpp
inline bool ContinueAsyncOperation();
```

### <a name="return-value"></a>Dönüş Değeri

`true` zaman uyumsuz işlemi geçerli durumu ise *çalışmaya*, yani işlemi devam etmelidir. Aksi takdirde `false`, yani işlemi durdurmak.

## <a name="currentstatus"></a>AsyncBase::CurrentStatus

Geçerli zaman uyumsuz işlemin durumunu alır.

```cpp
inline void CurrentStatus(
   Details::AsyncStatusInternal *status
);
```

### <a name="parameters"></a>Parametreler

*Durumu*<br/>
Bu işlem geçerli durumu depoladığı konum.

### <a name="remarks"></a>Açıklamalar

Bu işlem, iş parçacığı açısından güvenlidir.

## <a name="errorcode"></a>AsyncBase::ErrorCode

Geçerli zaman uyumsuz işlem hata kodunu alır.

```cpp
inline void ErrorCode(
   HRESULT *error
);
```

### <a name="parameters"></a>Parametreler

*Hata*<br/>
Bu işlem, geçerli hata kodu depoladığı konum.

### <a name="remarks"></a>Açıklamalar

Bu işlem, iş parçacığı açısından güvenlidir.

## <a name="firecompletion"></a>AsyncBase::FireCompletion

Tamamlanma olayı işleyicisini çağırır veya iç ilerleme temsilci sıfırlar.

```cpp
void FireCompletion(
   void
) override;

virtual void FireCompletion();
```

### <a name="remarks"></a>Açıklamalar

Ürününün ilk sürümünü `FireCompletion()` iç ilerleme temsilci değişkeni sıfırlar. Zaman uyumsuz işlem tamamlandıysa ikinci sürüm tamamlama olay işleyicisini çağırır.

## <a name="fireprogress"></a>AsyncBase::FireProgress

Geçerli ilerleme olay işleyicisini çağırır.

```cpp
void FireProgress(
   const typename ProgressTraits::Arg2Type arg
);
```

### <a name="parameters"></a>Parametreler

*bağımsız değişken*<br/>
Çağrılacak olay işleyicisi yöntemi.

### <a name="remarks"></a>Açıklamalar

`ProgressTraits` türetilen [ArgTraitsHelper yapısı](../windows/argtraitshelper-structure.md).

## <a name="get-errorcode"></a>AsyncBase::get_ErrorCode

Geçerli zaman uyumsuz işlem hata kodunu alır.

```cpp
STDMETHOD(
   get_ErrorCode
)(HRESULT* errorCode) override;
```

### <a name="parameters"></a>Parametreler

*hata kodu*<br/>
Geçerli hata kodu nerede depolandığını konumu.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, geçerli zaman uyumsuz işlemin kapatılırsa E_ILLEGAL_METHOD_CALL.

## <a name="get-id"></a>Asyncbase::get_ıd

Zaman uyumsuz işlem tanıtıcısını alır.

```cpp
STDMETHOD(
   get_Id
)(unsigned int *id) override;
```

### <a name="parameters"></a>Parametreler

*id*<br/>
Tanıtıcı depolanacak bulunduğu konumu.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, E_ILLEGAL_METHOD_CALL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem `IAsyncInfo::get_Id`.

## <a name="get-status"></a>AsyncBase::get_Status

Zaman uyumsuz işlemin durumunu gösteren bir değer alır.

```cpp
STDMETHOD(
   get_Status
)(AsyncStatus *status) override;
```

### <a name="parameters"></a>Parametreler

*Durumu*<br/>
Durum depolanacak bulunduğu konumu. Daha fazla bilgi için `Windows::Foundation::AsyncStatus` sabit listesi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, E_ILLEGAL_METHOD_CALL.

### <a name="remarks"></a>Açıklamalar

Bu yöntem `IAsyncInfo::get_Status`.

## <a name="getoncomplete"></a>AsyncBase::GetOnComplete

Adres geçerli tamamlama olay işleyicisinin belirtilen değişkenine kopyalar.

```cpp
STDMETHOD(
   GetOnComplete
)(TComplete** completeHandler);
```

### <a name="parameters"></a>Parametreler

*completeHandler*<br/>
Adres geçerli tamamlama olay işleyicisinin depolandığı konum.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, E_ILLEGAL_METHOD_CALL.

## <a name="getonprogress"></a>AsyncBase::GetOnProgress

Adres geçerli ilerleme olay işleyicisinin belirtilen değişkenine kopyalar.

```cpp
STDMETHOD(
   GetOnProgress
)(TProgress** progressHandler);
```

### <a name="parameters"></a>Parametreler

*progressHandler*<br/>
Adres geçerli ilerleme olay işleyicisinin depolandığı konum.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, E_ILLEGAL_METHOD_CALL.

## <a name="oncancel"></a>AsyncBase::OnCancel

Türetilen bir sınıfta geçersiz kılındığında, bir zaman uyumsuz işlem iptal eder.

```cpp
virtual void OnCancel(
   void
) = 0;
```

## <a name="onclose"></a>AsyncBase::OnClose

Türetilen bir sınıfta geçersiz kılındığında, zaman uyumsuz bir işlem kapatır.

```cpp
virtual void OnClose(
   void
) = 0;
```

## <a name="onstart"></a>AsyncBase::OnStart

Türetilen bir sınıfta geçersiz kılındığında, zaman uyumsuz bir işlem başlatır.

```cpp
virtual void OnStart(
   void
) = 0;
```

## <a name="put-id"></a>Asyncbase::put_ıd

Zaman uyumsuz işlem tanıtıcısı ayarlar.

```cpp
STDMETHOD(
   put_Id
)(const unsigned int id);
```

### <a name="parameters"></a>Parametreler

*id*<br/>
Sıfır dışında bir tanıtıcı.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde E_INVALIDARG veya E_ILLEGAL_METHOD_CALL.

## <a name="putoncomplete"></a>AsyncBase::PutOnComplete

Tamamlama olay işleyicisinin adresi belirtilen değere ayarlar.

```cpp
STDMETHOD(
   PutOnComplete
)(TComplete* completeHandler);
```

### <a name="parameters"></a>Parametreler

*completeHandler*<br/>
İstediğiniz tamamlama olay işleyicisinin nasıl ayarlandığını adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, E_ILLEGAL_METHOD_CALL.

## <a name="putonprogress"></a>AsyncBase::PutOnProgress

Devam eden olay işleyicisinin adresi belirtilen değere ayarlar.

```cpp
STDMETHOD(
   PutOnProgress
)(TProgress* progressHandler);
```

### <a name="parameters"></a>Parametreler

*progressHandler*<br/>
İstediğiniz ilerleme olay işleyicisinin nasıl ayarlandığını adresi.

### <a name="return-value"></a>Dönüş Değeri

Başarılıysa S_OK; Aksi takdirde, E_ILLEGAL_METHOD_CALL.

## <a name="start"></a>AsyncBase::Start

Zaman uyumsuz işlemi başlatır.

```cpp
STDMETHOD(
   Start
)(void);
```

### <a name="return-value"></a>Dönüş Değeri

İşlemi başlatıldığında veya zaten varsa S_OK başlatıldı; Aksi takdirde, E_ILLEGAL_STATE_CHANGE.

### <a name="remarks"></a>Açıklamalar

`Start()` bir varsayılan uygulamasıdır `IAsyncInfo::Start`, ve hiçbir asıl işi yapar. Aslında bir zaman uyumsuz işlemi başlatmak için geçersiz kılma `OnStart()` saf sanal yöntemi.

## <a name="trytransitiontocompleted"></a>AsyncBase::TryTransitionToCompleted

Geçerli zaman uyumsuz işlem tamamlanıp tamamlanmadığını gösterir.

```cpp
bool TryTransitionToCompleted(
   void
);
```

### <a name="return-value"></a>Dönüş Değeri

`true` zaman uyumsuz işlem tamamlandıysa; Aksi takdirde, `false`.

## <a name="trytransitiontoerror"></a>AsyncBase::TryTransitionToError

Belirtilen hata kodu iç hata durumunda değiştirip değiştiremeyeceğini belirtir.

```cpp
bool TryTransitionToError(
   const HRESULT error
);
```

### <a name="parameters"></a>Parametreler

*Hata*<br/>
HRESULT hatası.

### <a name="return-value"></a>Dönüş Değeri

`true` İç hata durumu değiştirildi Aksi takdirde, `false`.

### <a name="remarks"></a>Açıklamalar

Bu işlem, yalnızca hata durumunda S_OK için zaten ayarlanmışsa hata durumu değiştirir. Hata durumunda zaten iptal edildi, tamamlandı veya kapalı hata olması durumunda bu işlem bir etkisi yoktur.
