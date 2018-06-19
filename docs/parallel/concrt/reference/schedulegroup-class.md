---
title: ScheduleGroup sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- ScheduleGroup
- CONCRT/concurrency::ScheduleGroup
- CONCRT/concurrency::ScheduleGroup::Id
- CONCRT/concurrency::ScheduleGroup::Reference
- CONCRT/concurrency::ScheduleGroup::Release
- CONCRT/concurrency::ScheduleGroup::ScheduleTask
dev_langs:
- C++
helpviewer_keywords:
- ScheduleGroup class
ms.assetid: 86d380ff-f2e8-411c-b1a8-22bd3079824a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cf679abbeb1134332d98ef0bd2ba8f2b845d30a4
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688693"
---
# <a name="schedulegroup-class"></a>ScheduleGroup Sınıfı
Bir zamanlama grubu için bir Özet temsil eder. Zamanlama grupları bir dizi ilgili iş geçici olarak, başka bir gruba geçmeden önce aynı gruptaki başka bir görev yürütme ya da dağınık şekilde, aynı aynı grubu içindeki birden çok öğe çalıştırarak birbirine yakın zamanlanma gelen o avantajları düzenleyin. NUMA düğümü veya fiziksel yuva.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
class ScheduleGroup;
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="protected-constructors"></a>Korumalı Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[~ ScheduleGroup yok Edicisi](#dtor)||  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Kimliği](#id)|Grubun ait olduğu Zamanlayıcı içinde benzersizdir zamanlama grubu için bir tanımlayıcı döndürür.|  
|[Başvuru](#reference)|Zamanlama Grup başvurusu sayısını artırır.|  
|[Sürüm](#release)|Azaltır Zamanlayıcı Grup başvurusu sayısı.|  
|[ScheduleTask](#scheduletask)|Hafif görev zamanlama grubundaki zamanlar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `ScheduleGroup`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** concrt.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="id"></a> Kimliği 

 Grubun ait olduğu Zamanlayıcı içinde benzersizdir zamanlama grubu için bir tanımlayıcı döndürür.  
  
```
virtual unsigned int Id() const = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Grubun ait olduğu Zamanlayıcı içinde benzersizdir zamanlama grubu için bir tanımlayıcı.  
  
##  <a name="operator_delete"></a> delete işleci 

 A `ScheduleGroup` nesne bozulur dahili olarak çalışma zamanı tarafından tüm dış başvuruları yayımlandığında. Açıkça silinemiyor.  
  
```
void operator delete(
    void* _PObject);

void operator delete(
    void* _PObject,
    int,
 const char *,
    int);
```    
  
### <a name="parameters"></a>Parametreler  
 `_PObject`  
 Silinecek nesne için bir işaretçi.  
  
##  <a name="reference"></a> Başvuru 

 Zamanlama Grup başvurusu sayısını artırır.  
  
```
virtual unsigned int Reference() = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni artırılır başvuru sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu, genellikle zamanlama Grup birleşim için kullanım ömrünü yönetmek için kullanılır. Bir zamanlama grubu başvuru sayısı sıfıra düşerse, zamanlama Grup çalışma zamanı tarafından silindi. Ya da kullanılarak oluşturulan bir zamanlama grubu [CurrentScheduler::CreateScheduleGroup](currentscheduler-class.md#createschedulegroup) yöntemini veya [Scheduler::CreateScheduleGroup](scheduler-class.md#createschedulegroup) yöntemi başlar bir başvuru sayısına.  
  
##  <a name="release"></a> Sürüm 

 Azaltır Zamanlayıcı Grup başvurusu sayısı.  
  
```
virtual unsigned int Release() = 0;
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni indirildiği başvuru sayısı.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu, genellikle zamanlama Grup birleşim için kullanım ömrünü yönetmek için kullanılır. Bir zamanlama grubu başvuru sayısı sıfıra düşerse, zamanlama Grup çalışma zamanı tarafından silindi. Adlı sonra `Release` yöntemi oluşturma kaldırmak için belirli sayıda başvuru sayısı ve kullanılarak yerleştirilen herhangi bir ek başvurular `Reference` yöntemi, daha fazla zamanlama Grup kullanan olamaz. Bunun yapılması tanımsız davranışlara neden.  
  
 Belirli Zamanlayıcı örneği ile ilişkili bir zamanlama grubudur. Zamanlayıcı tüm başvurularını serbest önce ikinci yok zamanlayıcıda neden olabilir çünkü zamanlama Grup yapılan tüm başvuruları yayımlanan emin olmanız gerekir. Tanımsız davranış aksi sonuçlarında yapılıyor.  
  
##  <a name="dtor"></a> ~ ScheduleGroup 

```
virtual ~ScheduleGroup();
```  
  
##  <a name="scheduletask"></a> ScheduleTask 

 Hafif görev zamanlama grubundaki zamanlar.  
  
```
virtual void ScheduleTask(
    TaskProc _Proc,
    _Inout_opt_ void* _Data) = 0;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Proc`  
 İşlev gövdesi hafif görev gerçekleştirmek için bir işaretçi.  
  
 `_Data`  
 Görev gövdesi için parametre olarak geçirilen verileri void işaretçi.  
  
### <a name="remarks"></a>Açıklamalar  
 Çağırma `ScheduleTask` yöntemi örtük olarak yerleştirir başvuru sayısı çalışma zamanı tarafından görev yürütüldükten sonra uygun bir zamanda kaldırılan zamanlama grubunda.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace](concurrency-namespace.md)   
 [CurrentScheduler sınıfı](currentscheduler-class.md)   
 [Zamanlayıcı sınıfı](scheduler-class.md)   
 [Görev Zamanlayıcısı](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)



