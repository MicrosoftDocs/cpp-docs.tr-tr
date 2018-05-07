---
title: Platform::WeakReference sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- Platform::WeakReference
ms.assetid: 8cfe1977-a8c7-4b7b-b539-25c77ed4c5f1
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a8db5c855b6a377a0202183d48b8fd34e93b6072
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="platformweakreference-class"></a>Platform::WeakReference sınıfı
Ref sınıfının bir örneği zayıf başvuru temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp 
class WeakReference  
```  
  
#### <a name="parameters"></a>Parametreler  
  
### <a name="members"></a>Üyeler  
  
### <a name="constructors"></a>Oluşturucular  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[WeakReference::WeakReference](#ctor)|WeakReference sınıfı yeni bir örneğini başlatır.|  
  
### <a name="methods"></a>Yöntemler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[WeakReference::Resolve](#resolve)|Nesne artık varsa bir tanıtıcı temel ref sınıfı veya nullptr döndürür.|  
  
### <a name="operators"></a>İşleçler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[WeakReference::operator =](#operator-assign)|Yeni bir değer WeakReference nesneye atar.|  
|[WeakReference::operator BoolType](#booltype)|Güvenli bool deseni uygular.|  
  
### <a name="remarks"></a>Açıklamalar  
 WeakReference sınıfı ref sınıfı değil ve bu nedenle Platform::Object devralmıyor ^ ve bir genel yöntem imzada kullanılamaz.  

## <a name="operator-assign"></a> WeakReference::operator =
Bir değer için bir WeakReference atar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
WeakReference& operator=(decltype(__nullptr));    
WeakReference& operator=(const WeakReference& otherArg);   
WeakReference& operator=(WeakReference&& otherArg);    
WeakReference& operator=(const volatile ::Platform::Object^ const otherArg); 
```  
  
### <a name="remarks"></a>Açıklamalar  
 Yukarıdaki listede son aşırı WeakReference değişkenine ref sınıfı atamanızı sağlar. Bu durumda ref alta sınıftır [Platform::Object](../cppcx/platform-object-class.md)^. Özgün türü daha sonra tür parametresi için bağımsız değişken olarak belirterek geri [WeakReference::Resolve\<T >](#resolve) üye işlevi.  
  
## <a name="booltype"></a> WeakReference::operator BoolType
WeakReference sınıfı için güvenli bool deseni uygular. Açıkça kodunuzdan çağrılması değil.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
BoolType BoolType()  
```  

## <a name="resolve"></a> WeakReference::Resolve yöntemi (Platform ad alanı)
Özgün ref sınıfı için bir işleyici döner veya `nullptr` nesne artık yoksa.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
template<typename T>  
T^ Resolve() const  
```  
  
### <a name="parameters"></a>Parametreler  
  
### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 WeakReference nesne daha önce ilişkili ref sınıfı veya nullptr işleyici.  
  
### <a name="example"></a>Örnek  
 Bu kod örneği açıklamasıdır.  
  
```  
  
Bar^ bar = ref new Bar();  
//use bar...  
  
if (bar != nullptr)  
{  
    WeakReference wr(bar);  
    Bar^ newReference = wr.Resolve<Bar>();  
}  
```  
  
 Tür parametresi T, değil T olduğuna dikkat edin ^.  
  
 
## <a name="ctor"></a> WeakReference::WeakReference Oluşturucusu
Bir WeakReference oluşturmak için çeşitli yöntemler sağlar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
WeakReference();  
WeakReference(decltype(__nullptr));  
WeakReference(const WeakReference& otherArg);  
WeakReference(WeakReference&& otherArg);  
explicit WeakReference(const volatile ::Platform::Object^ const otherArg);  
```  
### <a name="example"></a>Örnek  
  
```cpp    
MyClass^ mc = ref new MyClass();  
WeakReference wr(mc);  
MyClass^ copy2 = wr.Resolve<MyClass>();    
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)