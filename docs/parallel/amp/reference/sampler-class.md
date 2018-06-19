---
title: sampler sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- sampler
- AMP_GRAPHICS/sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::sampler
- AMP_GRAPHICS/concurrency::sampler::graphics::get_address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::get_border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::get_filter_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::address_mode
- AMP_GRAPHICS/concurrency::sampler::graphics::border_color
- AMP_GRAPHICS/concurrency::sampler::graphics::filter_mode
dev_langs:
- C++
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f9788b62385f7c6f5eb82e3fbc69d63d3120cc2
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693357"
---
# <a name="sampler-class"></a>sampler Sınıfı
Sampler sınıfı doku örnekleme için kullanılacak örnekleme yapılandırma bilgilerini toplar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
class sampler;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[sampler Oluşturucusu](#ctor)|Fazla Yüklendi. Bir örneği örneği oluşturur.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[get_address_mode](#get_address_mode)|Döndürür `address_mode` örneği nesnesiyle ilişkili.|  
|[get_border_color](#get_border_color)|Sampler nesnesiyle ilişkili kenarlık rengi döndürür.|  
|[get_filter_mode](#get_filter_mode)|Döndürür `filter_mode` örneği nesnesiyle ilişkili.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator=](#operator_eq)|Fazla Yüklendi. Atama işleci.|  
  
### <a name="public-data-members"></a>Ortak Veri Üyeleri  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[address_mode](#address_mode)|Adres modunu alır `sampler` nesnesi.|  
|[border_color](#border_color)|Kenarlık rengini alır `sampler` nesnesi.|  
|[filter_mode](#filter_mode)|Filtre modunu alır `sampler` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `sampler`  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp_graphics.h  
  
 **Namespace:** concurrency::graphics  
  
##  <a name="ctor"></a> örneği 

 Bir örneğini oluşturur [sampler sınıfı](sampler-class.md).  
  
```  
sampler() restrict(cpu);

 *// [1] default constructor  
 
sampler(// [2] constructor  
    filter_mode _Filter_mode) restrict(cpu);

 
sampler(// [3] constructor  
    address_mode _Address_mode,  
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

 
sampler(// [4] constructor  
    filter_mode _Filter_mode,  
    address_mode _Address_mode,  
    float_4 _Border_color = float_4(0.0f,
    0.0f,
    0.0f,
    0.0f)) restrict(cpu);

 
sampler(// [5] copy constructor  
    const sampler& _Other) restrict(amp,
    cpu);

 
sampler(// [6] move constructor  
    sampler&& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Filter_mode`  
 Örnekleme içinde kullanılacak filtre modu.  
  
 `_Address_mode`  
 Tüm boyutlar için örnekleme içinde kullanılacak adresleme modu.  
  
 `_Border_color`  
 Adres modu address_border ise kullanılacak kenarlık rengi. Varsayılan değer `float_4(0.0f, 0.0f, 0.0f, 0.0f)` şeklindedir.  
  
 `_Other`  
 [5] kopya Oluşturucu  
 `sampler` Yeni içine kopyalamak için nesne `sampler` örneği.  
  
 [6] taşıma Oluşturucusu  
 `sampler` Yeni içine taşımak için nesne `sampler` örneği.  
  
##  <a name="address_mode"></a> address_mode 

 Adres modunu alır `sampler` nesnesi.  
  
```  
__declspec(property(get= get_address_mode)) Concurrency::graphics::address_mode address_mode;  
```  
  
##  <a name="border_color"></a> border_color 

 Kenarlık rengini alır `sampler` nesnesi.  
  
```  
__declspec(property(get= get_border_color)) Concurrency::graphics::float_4 border_color;  
```  
  
##  <a name="filter_mode"></a> filter_mode 

 Filtre modunu alır `sampler` nesnesi.  
  
```  
__declspec(property(get= get_filter_mode)) Concurrency::graphics::filter_mode filter_mode;  
```  
  
##  <a name="get_address_mode"></a> get_address_mode 

 Bunun için yapılandırılmış filtre modu döndürür `sampler`.  
  
```  
Concurrency::graphics::address_mode get_address_mode() const __GPU;  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Örneği için yapılandırılmış adres modu.  
  
##  <a name="get_border_color"></a> get_border_color 

 Bunun için yapılandırılmış kenarlık rengini döndüren `sampler`.  
  
```  
Concurrency::graphics::float_4 get_border_color() const restrict(amp, cpu);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Kenarlık rengi içeren float_4.  
  
##  <a name="get_filter_mode"></a> get_filter_mode 

 Bunun için yapılandırılmış filtre modu döndürür `sampler`.  
  
```  
Concurrency::graphics::filter_mode get_filter_mode() const restrict(amp, cpu);
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Örneği için yapılandırılmış filtre modu.  
  
##  <a name="operator_eq"></a> işleç = 

 Var olan bir örneği için başka bir örneği nesnenin değeri atar.  
  
```  
sampler& operator= (// [1] copy assignment operator const sampler& _Other) restrict(amp,
    cpu);

 
sampler& operator= (// [2] move assingment operator sampler&& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 [1] kopya atama işleci  
 `sampler` Bu kopyalamak için nesne `sampler`.  
  
 [2] taşıma atama işleci  
 `sampler` Bu taşımak için nesne `sampler`.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu örneği örneğine başvuru.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Concurrency::graphics Ad Alanı](concurrency-graphics-namespace.md)
