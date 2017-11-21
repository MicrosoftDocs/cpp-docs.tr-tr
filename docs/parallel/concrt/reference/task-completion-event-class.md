---
title: "task_completion_event sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- task_completion_event
- PPLTASKS/concurrency::task_completion_event
- PPLTASKS/concurrency::task_completion_event::task_completion_event
- PPLTASKS/concurrency::task_completion_event::set
- PPLTASKS/concurrency::task_completion_event::set_exception
dev_langs: C++
helpviewer_keywords: task_completion_event class
ms.assetid: fb19ed98-f245-48dc-9ba5-487ba879b28a
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 78c5cb9bdd1da0876abacda48000a914c884d25a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="taskcompletionevent-class"></a>task_completion_event Sınıfı
`task_completion_event` Sınıfı, bir koşul sağlanırsa kadar bir görevi yürütme gecikme veya dış bir olaya yanıt olarak bir görevi başlatmak olanak sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename _ResultType>
class task_completion_event;

template<>
class task_completion_event<void>;
```  
  
#### <a name="parameters"></a>Parametreler  
 `_ResultType`  
 Bu sonuç türü `task_completion_event` sınıfı.  
  
 `T`  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[task_completion_event](#ctor)|Oluşturan bir `task_completion_event` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[ayarlama](#set)|Fazla Yüklendi. Görev tamamlama olayını ayarlar.|  
|[set_exception](#set_exception)|Fazla Yüklendi. Bu olayla ilişkili tüm görevler için bir özel durum yayar.|  
  
## <a name="remarks"></a>Açıklamalar  
 Senaryonuz tamamlayacak bir görev oluşturmak gerektirir ve böylelikle kendi devamlılıklar gelecekte bir noktada yürütme zamanlanan sahip olduğunda bir görev tamamlama olayı oluşturulan bir görev kullanın. `task_completion_event` , Oluşturma ve görev tamamlama olayı bu tür bir değerle kümesi metodunun çağrılması ilişkili görevinin tamamlanması için neden ve bu değeri sonuç olarak kendi devamlılığını sağlar görev aynı türde olmalıdır.  
  
 Görev tamamlama olayını hiçbir zaman işaret edildiyse, destructed olduğunda oluşturulan tüm görevler iptal edilir.  
  
 `task_completion_event`Akıllı bir işaretçi gibi davranır ve değere göre geçirilecek.  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `task_completion_event`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ppltasks.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="set"></a>ayarlama 

 Görev tamamlama olayını ayarlar.  
  
```
bool set(_ResultType _Result) const ;

bool set() const ;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Result`  
 Bu olay ile ayarlamak için sonucu.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yöntem `true` olay ayarı başarılı olduysa. Döndürdüğü `false` olay zaten ayarlanmışsa.  
  
### <a name="remarks"></a>Açıklamalar  
 Birden çok varlığında veya aynı anda yapılan `set`, sadece ilk çağrı başarısız olur ve sonuç (varsa) görev tamamlama olayı depolanır. Kalan ayarlar dikkate alınmaz ve yöntemi false döndürür. Bir görev tamamlama olayı ayarladığınızda, tüm görevler olay hemen tamamlanır ve varsa, kendi devamlılıklar zamanlanacak oluşturulduğu. Görev tamamlama nesneleri bir `_ResultType` dışında `void` değeri kendi devamlılıklar geçer.  
  
##  <a name="set_exception"></a>set_exception 

 Bu olayla ilişkili tüm görevler için bir özel durum yayar.  
  
```
template<typename _E>
__declspec(noinline) bool set_exception(_E _Except) const;

__declspec(noinline) bool set_exception(std::exception_ptr _ExceptionPtr) const ;
```  
  
### <a name="parameters"></a>Parametreler  
 `_E`  
 `_Except`  
 `_ExceptionPtr`  
  
### <a name="return-value"></a>Dönüş Değeri  
  
##  <a name="ctor"></a>task_completion_event 

 Oluşturan bir `task_completion_event` nesnesi.  
  
```
task_completion_event();
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)
