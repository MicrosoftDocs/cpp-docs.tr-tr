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
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 79c7824a64fc9bfa4bef761e82505195835146ef
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33090532"
---
# <a name="platformcomexception-class"></a>Platform::COMException sınıfı
Uygulama yürütmesi sırasında oluşan COM hataları temsil eder. COMException bir dizi önceden tanımlanmış, standart özel durumlar için temel sınıftır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
public ref class COMException : Exception,    IException,    IPrintable,    IEquatable  
```  
  
### <a name="members"></a>Üyeler  
 COMException sınıfı nesne sınıfı ve IException, IPrintable ve IEquatable arabirimlerinden devralır.  
  
 COMException üyelerinin aşağıdaki türleri de vardır.  
  
 **Oluşturucular**  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[COMException](#ctor)|COMException sınıfının yeni bir örneğini başlatır.|  
  
 **Yöntemler**  
  
 COMException sınıfı Equals(), Finalize(), GetHashCode(), GetType(), MemberwiseClose() ve ToString() yöntemleri devralır [Platform::Object sınıfı](../cppcx/platform-object-class.md).  
  
 **Özellikler**  
  
 COMException sınıfı aşağıdaki özelliklere sahiptir.  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[Exception::HResult](#hresult)|Özel durumu karşılık gelen HRESULT.|  
|[Exception::Message](#message)|Özel durumu açıklayan ileti.|  
  
## <a name="derived-exceptions"></a>Türetilen özel durumlar  
 Aşağıdaki önceden tanımlanmış özel durumlar COMException türetilir. Bunların COMException farklı yalnızca kullanıcıların adı, kendi oluşturucusu ve arka plandaki HRESULT değerleri adı.  
  
|Ad|Temel alınan HRESULT|Açıklama|  
|----------|------------------------|-----------------|  
|COMException|*Kullanıcı tanımlı hresult*|Tanınmayan HRESULT bir COM yöntemi çağrısından döndürülen zaman oluşturulur.|  
|AccessDeniedException|E_ACCESSDENIED|Bir kaynak veya özellik için erişim reddedildi zaman oluşturulur.|  
|ChangedStateException|E_CHANGED_STATE|Bir koleksiyon yineleyici veya bir koleksiyon görünümü yöntemlerini yöntemi sonuçlarını geçersiz kılmalarını üst koleksiyon değiştikten sonra çağrıldığında oluşturulur.|  
|ClassNotRegisteredException|REGDB_E_CLASSNOTREG|Bir COM sınıfı kaydedilmemiş zaman oluşturulur.|  
|DisconnectedException|RPC_E_DISCONNECTED|Bir nesne istemcilerinden zaman oluşturulur.|  
|FailureException|E_FAIL|Bir işlem başarısız olduğunda oluşturulur.|  
|InvalidArgumentException|E_INVALIDARG|Bir yöntem için sağlanan bağımsız değişkenlerden biri geçerli değilse oluşturulur.|  
|InvalidCastException|E_NOINTERFACE|Bir başka bir türüne atanamaz zaman oluşturulur.|  
|NotImplementedException|E_NOTIMPL|Arabirim yöntemi bir sınıf üzerinde uygulanmadı dönerse oluşturulur.|  
|NullReferenceException|E_POINTER|Null Nesne başvurusu başvuru girişimi olduğunda oluşturulur.|  
|OperationCanceledException|E_ABORT|Bir işlem iptal edildiğinde oluşturulur.|  
|OutOfBoundsException|E_BOUNDS|Bir işlem, geçerli aralığın dışında veri erişim girişiminde bulunduğunda oluşur.|  
|OutOfMemoryException|E_OUTOFMEMORY|İşlemi tamamlamak için bellek yetersiz olduğunda oluşturulur.|  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Desteklenen en düşük sunucu:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Meta veriler:** platform.winmd  

## <a name="ctor"></a> COMException::COMException Oluşturucusu
COMException sınıfının yeni bir örneğini intializes.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
COMException( int hresult )  
```  
  
### <a name="parameters"></a>Parametreler  
 HRESULT  
 Özel durum tarafından temsil edilen HRESULT hata.  
  


## <a name="hresult"></a> COMException::HResult özelliği
Özel durumu karşılık gelen HRESULT.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:property int HResult {    int get();}  
```  
  
## <a name="property-value"></a>Özellik Değeri  
 Hata belirten bir HRESULT değeri.  
  
### <a name="remarks"></a>Açıklamalar  
 HRESULT değeri yorumlama hakkında daha fazla bilgi için bkz: [COM hata kodları yapısı](http://go.microsoft.com/fwlink/p/?LinkId=262045).  

## <a name="message"></a> COMException::Message özelliği
Özel durumu açıklayan ileti.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
public:property String^ Message {    String^ get();}  
```  
  
### <a name="property-value"></a>Özellik Değeri  
 Özel durum açıklaması.  
    

## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)