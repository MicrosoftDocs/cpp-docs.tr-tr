---
title: Platform::Agile sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- AGILE/Platform::Platform
- AGILE/Platform::Platform::Agile::Agile
- AGILE/Platform::Platform::Agile::Get
- AGILE/Platform::Platform::Agile::GetAddressOf
- AGILE/Platform::Platform::Agile::GetAddressOfForInOut
- AGILE/Platform::Platform::Agile::Release
dev_langs:
- C++
helpviewer_keywords:
- Platform::Agile
ms.assetid: e34459a9-c429-4c79-97fd-030c43ca4155
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4d7d2299dd1395e93f4cd88cbeaec6c0b9467308
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="platformagile-class"></a>Platform::Agile sınıfı
Bir MashalingBehavior olan bir nesneyi temsil eden standart çalışma zamanı özel durumları iş parçacığı oluşturma olasılığını önemli ölçüde azaltır Çevik bir nesne olarak =. `Agile<T>` Çağrısı veya aynı veya farklı bir iş parçacığı, çağrılması için Çevik olmayan nesnesi sağlar. Daha fazla bilgi için bkz: [iş parçacığı oluşturma ve hazırlama](../cppcx/threading-and-marshaling-c-cx.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <typename T>  
class Agile;  
```  
  
#### <a name="parameters"></a>Parametreler  
 T  
 Çevik olmayan sınıf için typename.  
  
### <a name="remarks"></a>Açıklamalar  
 Windows çalışma zamanı sınıflarda Çevik durumdadır. Çevik nesneyi çağırabilir veya işlem dışı veya işlem dışı nesne aynı veya farklı bir iş parçacığı tarafından çağrılabilir. Bir nesne Çevik değilse, Çevik olmayan nesne içinde kaymasını bir `Agile<T>` Çevik nesne. Ardından `Agile<T>` nesne sıralanmış ve Çevik olmayan nesnesini kullanılabilir.  
  
 `Agile<T>` Sınıfı bir yerel, standart C++ sınıfı ve gerektiriyor `agile.h`. Çevik olmayan nesne ve Çevik nesnesinin temsil ettiği *bağlamı*. Bağlam Çevik nesne modeli iş parçacığı oluşturma ve hazırlama davranışı belirtir. İşletim sistemi bağlamı nasıl hazırlanacağını nesneyi belirlemek için kullanır.  
  
### <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Agile::Agile](#ctor)|Çevik sınıfının yeni bir örneğini başlatır.|  
|[Çevik:: ~ Çevik yok Edicisi](#dtor)|Çevik sınıfının geçerli örneği yok eder.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Agile::get](#get)|Geçerli Çevik nesne tarafından temsil edilen nesne için bir işleyici döner.|  
|[Agile::GetAddressOf](#getaddressof)|Geçerli Çevik nesne yeniden başlatır ve ardından bir nesne türü için bir tanıtıcı adresini döndürür `T`.|  
|[Agile::GetAddressOfForInOut](#getaddressofforinout)|Geçerli Çevik nesne tarafından temsil edilen nesne için bir tanıtıcı adresini döndürür.|  
|[Agile::Release](#release)|Geçerli Çevik nesnenin nesnesini ve içerik atar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Agile::operator ->](#operator-arrow)|Geçerli Çevik nesne tarafından temsil edilen nesne için bir tanıtıcı alır.|  
|[Agile::operator=](#operator-assign)|Belirtilen değer geçerli Çevik nesneye atar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Object`  
  
 `Agile`  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Desteklenen en düşük sunucu:** Windows Server 2012  
  
 **Namespace:** Platform  
  
 **Başlık:** agile.h  

## <a name="ctor"></a>  Agile::Agile Oluşturucusu
Çevik sınıfının yeni bir örneğini başlatır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
 Agile();  
  
Agile(T^ object);   
  
Agile(const Agile<T>& object);  
  
Agile(Agile<T>&& object);  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Şablon typename parametresi tarafından belirtilen türü.  
  
 `object`  
 Bu oluşturucu, yeni bir Çevik örneği başlatmak için kullanılan nesneyi ikinci sürümü. Üçüncü sürümü, yeni Çevik örneğine kopyalanır nesne. Dördüncü sürümü, yeni Çevik örneğine taşınır nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 İlk bu oluşturucuyu varsayılan oluşturucu sürümüdür. İkinci sürümü tarafından belirtilen nesneden yeni Çevik örneği sınıfı başlatır `object` parametresi. Kopya Oluşturucu üçüncü sürümüdür. Taşıma Oluşturucusu dördüncü sürümüdür. Bu oluşturucu, özel durumlar oluşturulamıyor.  

## <a name="dtor"></a>  Çevik:: ~ Çevik yok Edicisi
Çevik sınıfının geçerli örneği yok eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
~Agile();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yıkıcı geçerli Çevik nesne tarafından temsil edilen nesne de serbest bırakır.  
  
## <a name="get"></a>   Agile::GET yöntemi
Geçerli Çevik nesne tarafından temsil edilen nesne için bir işleyici döner.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
   T^ Get() const  
;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli Çevik nesne tarafından temsil edilen nesne için bir tanıtıcı.  
  
 Dönüş değeri gerçekte belirlenmemiş iç tür türüdür. Dönüş değeri tutmak için uygun bir ile bildirilen bir değişken atamak üzere yoludur **otomatik** kesintisi anahtar sözcüğü yazın. Örneğin, `auto x = myAgileTvariable->Get();`.  
  
## <a name="getaddressof"></a>  Agile::GetAddressOf yöntemi
Geçerli Çevik nesne yeniden başlatır ve ardından bir nesne türü için bir tanıtıcı adresini döndürür `T`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
T^* GetAddressOf()   
throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Şablon typename parametresi tarafından belirtilen türü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir nesne türü için bir tanıtıcı adresini `T`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlem türünde bir nesne geçerli gösterimini serbest `T`, varsa; Çevik nesnenin veri üyeleri yeniden başlatır; geçerli iş parçacığı bağlamı; alır ve temsil edebilen bir tanıtıcı nesne değişkeni adresini döndürür bir Çevik olmayan nesne. Bir nesneyi temsil etmek Çevik sınıfı örneğini neden için atama işleci kullanın ([Agile::operator =](#operator-assign)) Çevik sınıf örneğine nesne atamak için.  

## <a name="getaddressofforinout"></a>  Agile::GetAddressOfForInOut yöntemi
Geçerli Çevik nesne tarafından temsil edilen nesne için bir tanıtıcı adresini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
T^* GetAddressOfForInOut()  throw();  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Şablon typename parametresi tarafından belirtilen türü.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli Çevik nesne tarafından temsil edilen nesne için bir tanıtıcı adresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlem geçerli iş parçacığı bağlamı alır ve ardından nesne temel alınan bir tanıtıcı adresini döndürür.  

## <a name="release"></a>  Agile::Release yöntemi
Geçerli Çevik nesnenin nesnesini ve içerik atar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
void Release() throw();  
  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli Çevik nesnenin nesnesini ve içerik, kaldıklarından ve ardından Çevik nesnenin değerini ayarlarsanız atılır null.  

## <a name="operator-arrow"></a>  Agile::operator -&gt; işleci
Geçerli Çevik nesne tarafından temsil edilen nesne için bir tanıtıcı alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
T^ operator->()   
const throw();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli Çevik nesne tarafından temsil edilen nesne için bir tanıtıcı.  
  
 Bu işleç gerçekte belirlenmemiş bir iç türü döndürür. Dönüş değeri tutmak için uygun bir ile bildirilen bir değişken atamak üzere yoludur **otomatik** kesintisi anahtar sözcüğü yazın.  

## <a name="operator-assign"></a>  Agile::operator = işleci
Belirtilen nesne geçerli Çevik nesneye atar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
   Agile<T> operator=(T^ object) throw();  
  
   Agile<T> operator=(  
      const Agile<T>& object  
) throw();  
  
   Agile<T> operator=(  
      Agile<T>&& object  
) throw();  
  
   T^ operator=(  
      IUnknown* lp  
) throw();  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Şablon typename tarafından belirtilen tür.  
  
 `object`  
 Nesne veya kopyaladığınız veya geçerli Çevik nesnesine taşınan bir nesne için tanıtıcı.  
  
 `lp`  
 IUnknown arabirimi işaretçisi bir nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bir nesne türü için bir tanıtıcı `T`  
  
### <a name="remarks"></a>Açıklamalar  
 Atama işleci ilk sürümü bir tanıtıcı bir başvuru türü geçerli Çevik nesnesine kopyalar. İkinci Sürüm bir Çevik bir başvuru türü geçerli Çevik nesnesine kopyalar. Bir Çevik yazın üçüncü sürüm taşır geçerli Çevik nesne. Dördüncü sürüm bir işaretçi bir COM nesnesi geçerli Çevik nesneye taşır.  
  
 Atama işlemi, geçerli Çevik nesne bağlamında otomatik olarak devam ettirir. 
       
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](platform-namespace-c-cx.md)