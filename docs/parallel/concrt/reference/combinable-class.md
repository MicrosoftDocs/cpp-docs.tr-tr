---
title: "combinable sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- combinable
- PPL/concurrency::combinable
- PPL/concurrency::combinable::combinable
- PPL/concurrency::combinable::clear
- PPL/concurrency::combinable::combine
- PPL/concurrency::combinable::combine_each
- PPL/concurrency::combinable::local
dev_langs:
- C++
helpviewer_keywords:
- combinable class
ms.assetid: fe0bfbf6-6250-47da-b8d0-f75369f0b5be
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a9bec5ce0e6679af71d8d3372fb939223691152a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/23/2018
---
# <a name="combinable-class"></a>combinable Sınıfı
`combinable<T>` Nesne kilidi serbest iş parçacığı yerel alt sırasında paralel algoritmalar hesaplamalar veri, iş parçacığı özel kopyasının sağlamak için tasarlanmıştır. Paralel işlemin sonunda, iş parçacığı özel alt hesaplamalar sonra nihai sonucu birleştirilebilir. Bu sınıf, paylaşılan bir değişken yerine kullanılabilir ve aksi durumda olurdu, çok sayıda paylaşılan değişken üzerinde Çekişme bir performans geliştirmesinden ortaya çıkabilir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```
template<typename T>
class combinable;
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Son birleştirilen sonucu veri türü. Tür kopya oluşturucu ve varsayılan bir oluşturucu sahip olmalıdır.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[combinable](#ctor)|Fazla Yüklendi. Yeni bir oluşturur `combinable` nesnesi.|  
|[~ combinable yok Edicisi](#dtor)|Bozar bir `combinable` nesnesi.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Temizle](#clear)|Herhangi bir önceki kullanımı hesaplama sonuçlarından Ara temizler.|  
|[combine](#combine)|Sağlanan birleştirme functor çağırarak iş parçacığı yerel alt hesaplamalar kümesinden son değeri hesaplar.|  
|[combine_each](#combine_each)|İş parçacığı yerel alt hesaplamalar kümesinden son bir değer, her iş parçacığı yerel alt hesaplama için bir kez sağlanan birleştirme functor çağırarak hesaplar. Nihai sonucu işlevi nesne tarafından toplanır.|  
|[Yerel](#local)|Fazla Yüklendi. İş parçacığı özel alt hesaplama bir başvuru döndürür.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator=](#operator_eq)|Atar bir `combinable` başka bir nesne `combinable` nesne.|  
  
## <a name="remarks"></a>Açıklamalar  
 Daha fazla bilgi için bkz: [paralel kapsayıcılar ve nesneler](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `combinable`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** ppl.h  
  
 **Namespace:** eşzamanlılık  
  
##  <a name="clear">Temizle</a> 

 Herhangi bir önceki kullanımı hesaplama sonuçlarından Ara temizler.  
  
```
void clear();
```  
  
##  <a name="ctor"></a> combinable 

 Yeni bir oluşturur `combinable` nesnesi.  
  
```
combinable();

template <typename _Function>
explicit combinable(_Function _FnInitialize);

combinable(const combinable& _Copy);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Function`  
 Başlatma functor nesnenin türü.  
  
 `_FnInitialize`  
 Her yeni iş parçacığı özel değer türü başlatmak için çağrılacak bir işlev `T`. İşlev çağırma işleci imzalı desteklemelidir `T ()`.  
  
 `_Copy`  
 Varolan bir `combinable` nesne bunu kopyalanacak.  
  
### <a name="remarks"></a>Açıklamalar  
 Yeni öğe türü için varsayılan oluşturucu ile ilk Oluşturucu başlatır `T`.  
  
 İkinci oluşturucu olarak sağlanan başlatma functor kullanarak yeni öğeleri başlatır `_FnInitialize` parametresi.  
  
 Üçüncü Oluşturucusu kopya Oluşturucu ' dir.  
  
##  <a name="dtor"></a> ~ combinable 

 Bozar bir `combinable` nesnesi.  
  
```
~combinable();
```  
  
##  <a name="combine"></a> Birleştirme 

 Sağlanan birleştirme functor çağırarak iş parçacığı yerel alt hesaplamalar kümesinden son değeri hesaplar.  
  
```
template<typename _Function>
T combine(_Function _FnCombine) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Function`  
 İki iş parçacığı yerel alt hesaplamalar birleştirmek için çağrılan işlev nesnesi türü.  
  
 `_FnCombine`  
 Alt hesaplamalar birleştirmek için kullanılan functor. Kendi imzası `T (T, T)` veya `T (const T&, const T&)`, ve ilişkilendirilebilir ve yer değiştirebilme olması gerekir.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Tüm iş parçacığı özel alt hesaplamalar birleştirmenin nihai sonucu.  
  
##  <a name="combine_each"></a> combine_each 

 İş parçacığı yerel alt hesaplamalar kümesinden son bir değer, her iş parçacığı yerel alt hesaplama için bir kez sağlanan birleştirme functor çağırarak hesaplar. Nihai sonucu işlevi nesne tarafından toplanır.  
  
```
template<typename _Function>
void combine_each(_Function _FnCombine) const;
```  
  
### <a name="parameters"></a>Parametreler  
 `_Function`  
 Tek bir iş parçacığı yerel alt hesaplama birleştirmek için çağrılan işlev nesnesi türü.  
  
 `_FnCombine`  
 Bir alt hesaplama birleştirmek için kullanılan functor. Kendi imzası `void (T)` veya `void (const T&)`ve ilişkilendirilebilir ve yer değiştirebilme olması gerekir.  
  
##  <a name="local">Yerel</a> 

 İş parçacığı özel alt hesaplama bir başvuru döndürür.  
  
```
T& local();

T& local(bool& _Exists);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Exists`  
 Bir Boole değeri referansı. Bu bağımsız değişkeni tarafından başvurulan Boole değeri ayarlanacak `true` alt hesaplama zaten bu iş parçacığında var ve kümesine `false` bu ilk alt hesaplama bu iş parçacığı üzerinde ise.  
  
### <a name="return-value"></a>Dönüş Değeri  
 İş parçacığı özel alt hesaplama referansı.  
  
##  <a name="operator_eq"></a> işleç = 

 Atar bir `combinable` başka bir nesne `combinable` nesne.  
  
```
combinable& operator= (const combinable& _Copy);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Copy`  
 Varolan bir `combinable` nesne bunu kopyalanacak.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu başvuru `combinable` nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı](concurrency-namespace.md)
