---
title: Platform::Array sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Array Constructors
- VCCORLIB/Namespace not found::Platform::Array::Value
dev_langs:
- C++
helpviewer_keywords:
- Platform::Array Class
ms.assetid: 7815ab40-88c5-42b0-83b8-081cef0cda31
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 65c45265714f869de10bdfd450c2b1349d6b526b
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34704678"
---
# <a name="platformarray-class"></a>Platform::Array sınıfı
Alınan ve uygulama ikili arabirimi (ABI) iletilen tek boyutlu, değiştirilebilir bir dizisini temsil eder.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp    
template <typename T>  
private ref class Array<TArg, 1> :   
    public WriteOnlyArray<TArg, 1>,  
    public IBoxArray<TArg>   
```  
  
### <a name="members"></a>Üyeler  
 Platform::Array devralan tüm alt yöntemleri [Platform::WriteOnlyArray sınıfı](../cppcx/platform-writeonlyarray-class.md) ve uygulayan `Value` özelliği [Platform::IBoxArray arabirimi](../cppcx/platform-iboxarray-interface.md).  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Dizi oluşturucular](#ctor)|Sınıf şablonu parametresi tarafından belirtilen türleri tek boyutlu, değiştirilebilir bir dizi başlatır *T*.|  
  
### <a name="methods"></a>Yöntemler  
 Bkz: [Platform::WriteOnlyArray sınıfı](../cppcx/platform-writeonlyarray-class.md).  
  
### <a name="properties"></a>Özellikler  
  
|||  
|-|-|  
|[Array::Value](#value)|Geçerli dizi için bir tanıtıcı alır.|  
  
### <a name="remarks"></a>Açıklamalar  
 Array sınıfı korumalı ve devralınan olamaz.  
  
 Windows çalışma zamanı tür sistemi basit diziler kavramını desteklemez ve bu nedenle bir IVector geçiremezsiniz < Platform::Array\<T >> bir dönüş değeri veya yöntem parametresi olarak. Basit bir dizi veya bir dizi sıraları ABI arasında geçirmek için kullanmak `IVector<IVector<T>^>`.  
  
 Ne zaman ve nasıl Platform::Array kullanılacağı hakkında daha fazla bilgi için bkz: [dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).  
  
 Windows çalışma zamanı tür sistemi basit diziler kavramını desteklemez ve bu nedenle bir IVector geçiremezsiniz < Platform::Array\<T >> bir dönüş değeri veya yöntem parametresi olarak. Basit bir dizi veya bir dizi sıraları ABI arasında geçirmek için kullanmak `IVector<IVector<T>^>`.  
  
 Bu sınıf, derleyici tarafından otomatik olarak dahil vccorlib.h başlığında tanımlanır. Platform.winmd içinde tanımlanan genel bir tür olduğundan IntelliSense ancak içinde değil Nesne Tarayıcısı görünür olur.  
  
### <a name="requirements"></a>Gereksinimler  
 Derleyici seçeneği: **/ZW**  

 
## <a name="ctor"></a>  Dizi oluşturucular
Sınıf şablonu parametresi tarafından belirtilen türleri tek boyutlu, değiştirilebilir bir dizi başlatır *T*.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp  
Array(unsigned int size);  
Array(T* data, unsigned int size);    
```  
  
#### <a name="parameters"></a>Parametreler  
 `T`  
 Şablon parametresi sınıfı.  
  
 `size`  
 Dizideki öğelerin sayısı  
  
 `data`  
 Bir dizi veri türü için bir işaretçi `T` bu dizi nesneyi başlatmak için kullanılır.  
  
### <a name="remarks"></a>Açıklamalar  
 Platform::Array örnekleri oluşturma hakkında daha fazla bilgi için bkz: [dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

## <a name="get"></a>  Array::GET yöntemi
Belirtilen dizin konumundaki dizi öğesi için bir başvuru alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp    
T& get(unsigned int index)  const;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `index`  
 Dizideki bir öğe tanımlayan sıfır tabanlı dizini. Minimum dizini 0 ve en büyük dizin ile belirtilen değer `size` parametresinde [Array Oluşturucusu](#ctor).  
  
### <a name="return-value"></a>Dönüş Değeri  
 Dizi öğesi tarafından belirtilen `index` parametresi.  
  
## <a name="value"></a>  Array::Value özelliği
Geçerli dizi için bir tanıtıcı alır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```cpp 
property Array^ Value;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Geçerli dizi için bir tanıtıcı.  

## <a name="see-also"></a>Ayrıca Bkz.  
 [Platform ad alanı](../cppcx/platform-namespace-c-cx.md)   
 [Dizi ve WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)