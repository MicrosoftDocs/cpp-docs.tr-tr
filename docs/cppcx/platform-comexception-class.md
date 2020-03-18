---
title: 'Platform:: COMException sınıfı'
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::COMException
- VCCORLIB/Platform::COMException::HResult
- VCCORLIB/Platform::COMException::Message
helpviewer_keywords:
- Platform::COMException Class
ms.assetid: 44fda4e5-574f-4d12-ab5f-4ff3f277448d
ms.openlocfilehash: 1d0d36ec16303d6bdaa5f2344cd5d48fba03c8bf
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79444300"
---
# <a name="platformcomexception-class"></a>Platform:: COMException sınıfı

Uygulama yürütme sırasında oluşan COM hatalarını temsil eder. COMException, bir dizi önceden tanımlanmış standart özel durum için temel sınıftır.

## <a name="syntax"></a>Sözdizimi

```cpp
public ref class COMException : Exception,    IException,    IPrintable,    IEquatable
```

### <a name="members"></a>Üyeler

COMException sınıfı, nesne sınıfından ve ıvınexception, ıyazdırılabilir ve IEquatable arabirimlerinden devralır.

COMException Ayrıca aşağıdaki üye türlerine sahiptir.

**Oluşturucular**

|Üye|Açıklama|
|------------|-----------------|
|[COMException](#ctor)|COMException sınıfının yeni bir örneğini başlatır.|

**Yöntemler**

COMException sınıfı, [Platform:: Object sınıfından](../cppcx/platform-object-class.md)Equals (), Finalize (), GetHashCode (), GetType (), MemberwiseClose () ve ToString () yöntemlerini devralır.

**Özellikler**

COMException sınıfı aşağıdaki özelliklere sahiptir.

|Üye|Açıklama|
|------------|-----------------|
|[Özel durum:: HResult](#hresult)|Özel duruma karşılık gelen HRESULT.|
|[Özel durum:: Ileti](#message)|Özel durumu açıklayan ileti.|

## <a name="derived-exceptions"></a>Türetilmiş özel durumlar

Aşağıdaki önceden tanımlanmış özel durumlar COMException öğesinden türetilir. Bunlar, COMException 'dan yalnızca kendi adında, oluşturucusunun adına ve temel alınan HRESULT değerine göre farklılık gösterir.

|Adı|Temel alınan HRESULT|Açıklama|
|----------|------------------------|-----------------|
|COMException|*Kullanıcı tanımlı HRESULT*|Bir COM yöntem çağrısından tanınmayan HRESULT döndürüldüğünde oluşturulur.|
|AccessDeniedException Oluşturucusu|E_ACCESSDENIED|Bir kaynak veya özelliğe erişim reddedildiğinde oluşturulur.|
|Changedstateexception Oluşturucusu|E_CHANGED_STATE|Üst koleksiyon değiştirildikten sonra bir koleksiyon yineleyici veya koleksiyon görünümü metotları çağrıldığında, yöntemin sonuçları geçersiz kılınırken oluşturulur.|
|Classnotregisteredexception Oluşturucusu|REGDB_E_CLASSNOTREG|Bir COM sınıfı kaydedilmemişse oluşturulur.|
|Disconnectedexception Oluşturucusu|RPC_E_DISCONNECTED|Bir nesnenin istemcileriyle bağlantısı kesildiğinde oluşturulur.|
|FailureException Oluşturucusu|E_FAIL|Bir işlem başarısız olduğunda oluşturulur.|
|InvalidArgumentException Oluşturucusu|E_INVALIDARG|Bir yönteme verilen bağımsız değişkenlerden biri geçerli değilse oluşturulur.|
|InvalidCastException|E_NOINTERFACE|Bir tür başka bir türe yayınlanatılamayacağını ortaya atılır.|
|NotImplementedException|E_NOTIMPL|Bir arabirim yöntemi bir sınıfa uygulanmadıysa oluşturulur.|
|Durumu|E_POINTER|Null nesne başvurusunu başvuru girişimi olduğunda oluşturulur.|
|OperationCanceledException|E_ABORT|Bir işlem iptal edildiğinde oluşturulur.|
|Outofboundsexception Oluşturucusu|E_BOUNDS|Bir işlem geçerli Aralık dışında veriye erişmeye çalıştığında oluşturulur.|
|OutOfMemoryException|E_OUTOFMEMORY|İşlemi gerçekleştirmek için yeterli bellek kalmadığında oluşturulur.|

### <a name="requirements"></a>Gereksinimler

**Desteklenen en düşük istemci:** Windows 8

**Desteklenen en düşük sunucu:** Windows Server 2012

**Ad alanı:** Platformunun

**Meta veri:** platform. winmd

## <a name="ctor"></a>COMException:: COMException Oluşturucusu

COMException sınıfının yeni bir örneğini başlattıktan sonra.

### <a name="syntax"></a>Sözdizimi

```cpp
COMException( int hresult )
```

### <a name="parameters"></a>Parametreler

*HRESULT*<br/>
Özel durumla temsil edilen HRESULT hatası.

## <a name="hresult"></a>COMException:: HResult özelliği

Özel duruma karşılık gelen HRESULT.

### <a name="syntax"></a>Sözdizimi

```cpp
public:
    property int HResult { int get();}
```

## <a name="property-value"></a>Özellik Değeri

Hatayı belirten bir HRESULT değeri.

### <a name="remarks"></a>Açıklamalar

HRESULT değerini yorumlama hakkında daha fazla bilgi için bkz. [com hata kodlarının yapısı](/windows/win32/com/structure-of-com-error-codes).

## <a name="message"></a>COMException:: Message özelliği

Özel durumu açıklayan ileti.

### <a name="syntax"></a>Sözdizimi

```cpp
public:property String^ Message {    String^ get();}
```

### <a name="property-value"></a>Özellik Değeri

Özel durumun açıklaması.

## <a name="see-also"></a>Ayrıca bkz.

[Platform ad alanı](../cppcx/platform-namespace-c-cx.md)
