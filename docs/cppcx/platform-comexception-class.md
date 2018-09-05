---
title: Platform::COMException sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::COMException
- VCCORLIB/Platform::Exception::HResult
- VCCORLIB/Platform::Exception::Message
dev_langs:
- C++
helpviewer_keywords:
- Platform::COMException Class
ms.assetid: 44fda4e5-574f-4d12-ab5f-4ff3f277448d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ef60fc542b38c7619ce7b65cc7f39db79ed1b228
ms.sourcegitcommit: a7046aac86f1c83faba1088c80698474e25fe7c3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/04/2018
ms.locfileid: "43679030"
---
# <a name="platformcomexception-class"></a>Platform::COMException sınıfı
Uygulama yürütme sırasında gerçekleşen COM hataları temsil eder. COMException bir dizi önceden tanımlanmış, standart özel durumlar için temel sınıftır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
public ref class COMException : Exception,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="members"></a>Üyeler  
 COMException sınıfı nesne sınıfı ve IException IPrintable ve IEquatable arabirimleri devralır.  
  
 COMException aşağıdaki üye türlerinden de vardır.  
  
 **Oluşturucular**  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[COMException](#ctor)|COMException sınıfının yeni bir örneğini başlatır.|  
  
 **Yöntemler**  
  
 COMException sınıfı ' lerin üzerine yaz, Finalize() ifadesini, GetHashCode(), GetType(), MemberwiseClose() ve ToString() yöntemler öğesinden devralan [Platform::Object sınıfı](../cppcx/platform-object-class.md).  
  
 **Özellikler**  
  
 COMException sınıfı aşağıdaki özelliklere sahiptir.  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[Exception::HResult](#hresult)|Özel duruma karşılık gelen HRESULT.|  
|[Exception::Message](#message)|Özel durumu açıklayan ileti.|  
  
## <a name="derived-exceptions"></a>Türetilen özel durumları  
 Aşağıdaki önceden tanımlanmış özel durumlar COMException türetilmiştir. COMException dışında da farklı olmaları yalnızca adında, oluşturucularına ve kendi temel HRESULT değerini adı.  
  
|Ad|Temel alınan HRESULT|Açıklama|  
|----------|------------------------|-----------------|  
|COMException|*Kullanıcı tanımlı hresult*|Tanınmayan HRESULT bir COM yöntem çağrısından döndürülen zaman oluşturulur.|  
|AccessDeniedException|E_ACCESSDENIED|Bir kaynağa veya özellik erişimi reddedilirse oluşturulur.|  
|ChangedStateException|E_CHANGED_STATE|Yöntemin sonuçları geçersiz kılmalarını üst koleksiyon değiştikten sonra bir koleksiyon yineleyici veya koleksiyon görünümü yöntemler çağrıldığında oluşturulur.|  
|ClassNotRegisteredException|REGDB_E_CLASSNOTREG|Bir COM sınıfı kaydedilmemiş olduğu zaman oluşturulur.|  
|DisconnectedException|RPC_E_DISCONNECTED|Bir nesnenin, istemcileriyle bağlantısı kesildiğinde oluşturulur.|  
|FailureException|E_FAIL|Bir işlemi başarısız olduğunda oluşturulur.|  
|InvalidArgumentException|E_INVALIDARG|Bir yöntem için sağlanan bağımsız değişkenlerden biri geçerli olmadığında oluşturulur.|  
|InvalidCastException|E_NOINTERFACE|Bir tür başka bir türe dönüştüremezsiniz zaman oluşturulur.|  
|NotImplementedException|E_NOTIMPL|Bir arabirim yöntemi, bir sınıf üzerinde uygulanmadı durum.|  
|NullReferenceException|E_POINTER|Bir null Nesne başvurusu başvuru girişimi olduğunda oluşturulur.|  
|OperationCanceledException|E_ABORT|Bir işlem iptal edildiğinde oluşturulur.|  
|OutOfBoundsException|E_BOUNDS|Bir işlem, geçerli aralığın dışında veri erişim girişiminde bulunduğunda oluşturulur.|  
|OutOfMemoryException|E_OUTOFMEMORY|İşlemi tamamlamak için bellek yetersiz olduğunda oluşturulur.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Sunucu desteklenen en düşük:** Windows Server 2012  
  
 **Namespace:** platformu  
  
 **Meta veri:** platform.winmd  

## <a name="ctor"></a> COMException::COMException Oluşturucusu
COMException sınıfının yeni bir örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
COMException( int hresult )  
```  
  
### <a name="parameters"></a>Parametreler  
 HRESULT  
 Özel durum tarafından temsil edilen HRESULT hatası.  
  


## <a name="hresult"></a> COMException::HResult özelliği
Özel duruma karşılık gelen HRESULT.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:property int HResult {    int get();}  
```  
  
## <a name="property-value"></a>Özellik Değeri  
 Hata belirten bir HRESULT değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 HRESULT değerini yorumlama hakkında daha fazla bilgi için bkz. [yapısı COM hata kodlarını](/windows/desktop/com/structure-of-com-error-codes).  

## <a name="message"></a> COMException::Message özelliği
Özel durumu açıklayan ileti.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:property String^ Message {    String^ get();}  
```  
  
### <a name="property-value"></a>Özellik Değeri  
 Özel durumun açıklaması.  
    

## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)