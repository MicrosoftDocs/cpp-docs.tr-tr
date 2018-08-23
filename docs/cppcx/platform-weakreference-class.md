---
title: Platform::WeakReference sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- Platform::WeakReference
ms.assetid: 8cfe1977-a8c7-4b7b-b539-25c77ed4c5f1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 77cd035b6cf84b16f4f6d5d92f3dd247f1251509
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/22/2018
ms.locfileid: "42601567"
---
# <a name="platformweakreference-class"></a>Platform::WeakReference sınıfı
Bir başvuru sınıfının bir örneğini zayıf bir başvuruyu temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp 
class WeakReference  
```  
  
#### <a name="parameters"></a>Parametreler  
  
### <a name="members"></a>Üyeler  
  
### <a name="constructors"></a>Oluşturucular  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[WeakReference::WeakReference](#ctor)|WeakReference sınıfının yeni bir örneğini başlatır.|  
  
### <a name="methods"></a>Yöntemler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[WeakReference::Resolve](#resolve)|Nesne artık mevcut değilse temel başvuru sınıfı veya nullptr için bir tanıtıcı döndürür.|  
  
### <a name="operators"></a>İşleçler  
  
|Üye|Açıklama|  
|------------|-----------------|  
|[WeakReference::operator =](#operator-assign)|WeakReference nesnesine yeni bir değer atar.|  
|[WeakReference::operator BoolType](#booltype)|Güvenli bool desenini uygular.|  
  
### <a name="remarks"></a>Açıklamalar  
 WeakReference sınıfı başvuru sınıfı değil ve bu nedenle Platform::Object devralmayan ^ ve genel bir yöntem imzasında kullanılamaz.  

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
 Son aşırı yükü, yukarıdaki listede bir başvuru sınıfının bir WeakReference değişkene atamanıza olanak sağlar. Bu durumda başvuru sınıfı alta [Platform::Object](../cppcx/platform-object-class.md)^. Özgün türü daha sonra tür parametresi için bağımsız değişken olarak belirterek geri [WeakReference::Resolve\<T >](#resolve) üye işlevi.  
  
## <a name="booltype"></a> WeakReference::operator BoolType
WeakReference sınıfı güvenli bool desenini uygular. Açıkça kodunuzdan çağrılması değil.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
BoolType BoolType()  
```  

## <a name="resolve"></a> WeakReference::Resolve yöntemi (Platform ad alanı)
Özgün başvuru sınıfı için bir tanıtıcı döndürür veya `nullptr` nesnesi artık mevcut değilse.  
  
### <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
template<typename T>  
T^ Resolve() const  
```  
  
### <a name="parameters"></a>Parametreler  
  
### <a name="property-valuereturn-value"></a>Özellik Değeri/Dönüş Değeri  
 WeakReference nesne daha önce ile ilişkilendirildi başvuru sınıfı veya nullptr tanıtıcı.  
  
### <a name="example"></a>Örnek  
 Bu kod örneği için açıklamasıdır.  
  
```  
  
Bar^ bar = ref new Bar();  
//use bar...  
  
if (bar != nullptr)  
{  
    WeakReference wr(bar);  
    Bar^ newReference = wr.Resolve<Bar>();  
}  
```  
  
 Tür parametresinin T, T değil olduğunu unutmayın ^.  
  
 
## <a name="ctor"></a> WeakReference::WeakReference Oluşturucusu
Bir WeakReference oluşturmak için çeşitli yollar sağlar.  
  
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