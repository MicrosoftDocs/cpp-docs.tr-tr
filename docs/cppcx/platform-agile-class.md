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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f552327156d9fc1abe5e921f3b59b1fb4132ff3d
ms.sourcegitcommit: 92dbc4b9bf82fda96da80846c9cfcdba524035af
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/05/2018
ms.locfileid: "43763438"
---
# <a name="platformagile-class"></a>Platform::Agile sınıfı
Bir MashalingBehavior sahip nesneyi temsil eden standart çalışma zamanı özel durumları iş parçacığı oluşturma olasılığını önemli ölçüde azaltan bir Çevik nesne olarak =. `Agile<T>` Çağrı veya aynı veya farklı bir iş parçacığı, çağrılması Çevik olmayan nesnesi sağlar. Daha fazla bilgi için [iş parçacığı oluşturma ve hazırlama](../cppcx/threading-and-marshaling-c-cx.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
template <typename T>  
class Agile;  
```  
  
#### <a name="parameters"></a>Parametreler  
 T  
 Çevik olmayan sınıf tür adı.  
  
### <a name="remarks"></a>Açıklamalar  
 Windows çalışma zamanı sınıflar Çevik çoğu. Çevik bir nesne çağırabilir veya bir işlemde veya işlem dışı nesnesi aynı veya farklı bir iş parçacığı tarafından çağrılabilir. Bir nesne Çevik değilse, Çevik olmayan nesneyi kaydırma bir `Agile<T>` Çevik olan nesne. Ardından `Agile<T>` nesne sıralanmış ve temel alınan Çevik olmayan nesne kullanılabilir.  
  
 `Agile<T>` Sınıfı yerel, standart bir C++ sınıfı ve gerektiriyor `agile.h`. Çevik olmayan nesne ve Çevik nesnesinin temsil ettiği *bağlam*. Bağlam, Çevik bir nesnenin modeli iş parçacığı oluşturma ve hazırlama davranışı belirtir. İşletim sistemi bağlamı nasıl hazırlanacağını nesneyi belirlemek için kullanır.  
  
### <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Agile::Agile](#ctor)|Çevik sınıfının yeni bir örneğini başlatır.|  
|[Çevik:: ~ Çevik yok Edicisi](#dtor)|Çevik sınıfının geçerli örneğini yok eder.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Agile::get](#get)|Geçerli Çevik nesne tarafından temsil edilen nesne için bir tanıtıcı döndürür.|  
|[Agile::GetAddressOf](#getaddressof)|Geçerli Çevik nesne yeniden başlatır ve ardından bir nesne türü için bir tanıtıcı adresini döndürür `T`.|  
|[Agile::GetAddressOfForInOut](#getaddressofforinout)|Geçerli Çevik nesne tarafından temsil edilen nesne için bir tanıtıcı adresini döndürür.|  
|[Agile::Release](#release)|Geçerli Çevik nesnenin nesnesini ve içerik atar.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Agile::operator ->](#operator-arrow)|Geçerli Çevik nesne tarafından temsil edilen nesne için tanıtıcı alır.|  
|[Agile::operator=](#operator-assign)|Belirtilen değer geçerli Çevik nesnesine atar.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `Object`  
  
 `Agile`  
  
### <a name="requirements"></a>Gereksinimler  
 **Desteklenen en düşük istemci:** Windows 8  
  
 **Sunucu desteklenen en düşük:** Windows Server 2012  
  
 **Namespace:** platformu  
  
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
 Typename şablon parametresi tarafından belirtilen bir tür.  
  
 `object`  
 Bu oluşturucu, yeni bir Çevik örneği başlatmak için kullanılan nesneyi ikinci sürümü. Üçüncü sürümü, yeni Çevik örneğine kopyalanan nesne. Dördüncü sürümü, yeni Çevik örneğine taşındığında nesne.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu oluşturucu ilk sürümü varsayılan oluşturucudur. Dosyanın ikinci sürümü yeni Çevik örneği sınıfı tarafından belirtilen bir nesneden başlatır `object` parametresi. Kopya Oluşturucu üçüncü sürümüdür. Taşıma Oluşturucu dördüncü sürümüdür. Bu oluşturucu, özel durumlar olamaz.  

## <a name="dtor"></a>  Çevik:: ~ Çevik yok Edicisi
Çevik sınıfının geçerli örneğini yok eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
~Agile();  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Bu yok Edicisi de geçerli Çevik nesne tarafından temsil edilen nesnenin serbest bırakır.  
  
## <a name="get"></a>   Agile::GET yöntemi
Geçerli Çevik nesne tarafından temsil edilen nesne için bir tanıtıcı döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
   T^ Get() const  
;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli Çevik nesne tarafından temsil edilen nesne için bir tanıtıcı.  
  
 Dönüş değeri gerçekten belirlenmemiş bir iç türü türüdür. Dönüş değerini tutmak için kullanışlı bir yol ile bildirilen bir değişken atamak için olan **otomatik** kesinti anahtar sözcüğü yazın. Örneğin, `auto x = myAgileTvariable->Get();`.  
  
## <a name="getaddressof"></a>  Agile::GetAddressOf yöntemi
Geçerli Çevik nesne yeniden başlatır ve ardından bir nesne türü için bir tanıtıcı adresini döndürür `T`.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
T^* GetAddressOf()   
throw();  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Typename şablon parametresi tarafından belirtilen bir tür.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Türünde bir nesne için tanıtıcı adresini `T`.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlem geçerli türü bir nesne temsili sürümleri `T`varsa; Çevik nesnenin veri üyeleri yeniden başlatır; geçerli iş parçacığı bağlamı; edinir ve ardından temsil edebilen bir tanıtıcı nesnesi değişkenin adresini döndürür bir Çevik olmayan nesne. Neden Çevik sınıfı örneğini temsil eden bir nesne için atama işlecini kullanın ([Agile::operator =](#operator-assign)) nesne Çevik sınıf örneğine atamak için.  

## <a name="getaddressofforinout"></a>  Agile::GetAddressOfForInOut yöntemi
Geçerli Çevik nesne tarafından temsil edilen nesne için bir tanıtıcı adresini döndürür.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
T^* GetAddressOfForInOut()  throw();  
  
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Typename şablon parametresi tarafından belirtilen bir tür.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli Çevik nesne tarafından temsil edilen nesne için tanıtıcı adresi.  
  
### <a name="remarks"></a>Açıklamalar  
 Bu işlem, geçerli iş parçacığı bağlamı alır ve temel alınan nesnenin bir tanıtıcı adresini döndürür.  

## <a name="release"></a>  Agile::Release yöntemi
Geçerli Çevik nesnenin nesnesini ve içerik atar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
void Release() throw();  
  
```  
  
### <a name="remarks"></a>Açıklamalar  
 Geçerli Çevik nesnenin nesnesini ve içerik, olduklarından ve Çevik bir nesnenin değerini ardından ayarlanırsa atılır null.  

## <a name="operator-arrow"></a>  Agile::operator -&gt; işleci
Geçerli Çevik nesne tarafından temsil edilen nesne için tanıtıcı alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
  
T^ operator->()   
const throw();  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli Çevik nesne tarafından temsil edilen nesne için bir tanıtıcı.  
  
 Bu işleç, aslında belirlenmemiş bir iç türü döndürür. Dönüş değerini tutmak için kullanışlı bir yol ile bildirilen bir değişken atamak için olan **otomatik** kesinti anahtar sözcüğü yazın.  

## <a name="operator-assign"></a>  Agile::operator = işleci
Belirtilen nesnenin geçerli Çevik nesnesine atar.  
  
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
 Nesne veya kopyaladığınız veya geçerli Çevik nesneye taşınan bir nesne için tanıtıcı.  
  
 `lp`  
 Bir nesnenin IUnknown arabirim işaretçisi.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Türünde bir nesne için tanıtıcı `T`  
  
### <a name="remarks"></a>Açıklamalar  
 Atama işleci ilk sürümü geçerli Çevik nesnesine bir başvuru türü bir tanıtıcı kopyalar. Bir Çevik bir başvuru türü için geçerli Çevik nesnesi ikinci sürüm kopyalar. Bir Çevik yazın üçüncü sürüm taşır geçerli Çevik nesne. Dördüncü sürümü bir COM nesnesi geçerli Çevik nesneye bir işaretçi taşır.  
  
 Atama işlemi, geçerli Çevik nesne bağlamı otomatik olarak devam ettirir. 
       
## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform Namespace](platform-namespace-c-cx.md)