---
title: CONCURRENCY::Graphics Namespace | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: AMP_GRAPHICS/Concurrency
dev_langs: C++
ms.assetid: 4529d3b1-d7da-4ffb-82bf-080915e0f23e
caps.latest.revision: "14"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ad53fea97c98f496d1140725f4232052e2f53d3b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="concurrencygraphics-namespace"></a>Concurrency::graphics Ad Alanı
Grafik ad alanı, türler ve grafik programlamaya için tasarlanmış işlevler sağlar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
namespace graphics;  
```  
  
## <a name="members"></a>Üyeler  
  
### <a name="namespaces"></a>Ad Alanları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[CONCURRENCY::Graphics:: Direct3D Namespace](concurrency-graphics-direct3d-namespace.md)|İşlevleri için Direct3D birlikte çalışabilirlik sağlar.|  
  
### <a name="typedefs"></a>Tür tanımları  
  
|Ad|Açıklama|  
|----------|-----------------|  
|`uint`|Öğe türü için [uint_2 sınıfı](uint-2-class.md), [uint_3 sınıfı](uint-3-class.md), ve [uint_4 sınıfı](uint-4-class.md). Olarak tanımlanan `typedef unsigned int uint;`.|  
  
### <a name="enumerations"></a>Numaralandırmalar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[address_mode numaralandırması](concurrency-graphics-namespace-enums.md#address_mode).|Doku örnekleme için desteklenen adresi modu belirtir.|  
|[filter_mode numaralandırması](concurrency-graphics-namespace-enums.md#filter_mode)|Doku örnekleme için desteklenen filtre modu belirtir.|  
  
### <a name="classes"></a>Sınıflar  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[texture sınıfı](texture-class.md)|Bir doku bir uzantı etki alanındaki bir accelerator_view üzerinde birleşik verilerdir. Değişkenleri, bir uzantı etki alanındaki her öğe için bir tane koleksiyonudur. Her bir değişken (imzasız int, int, float, çift) C++ ilkel türüne karşılık gelen bir değer tutan veya skaler tür norm veya unorm (concurrency::graphics içinde tanımlanmıştır) ya da uygun kısa vektör türleri concurrency::graphics tanımlanmış.|  
|[writeonly_texture_view sınıfı](writeonly-texture-view-class.md)|Bir writeonly_texture_view doku writeonly erişim sağlar.|  
|[double_2 sınıfı](double-2-class.md)|Kısa bir vektör 2 değerini temsil eden `double` değerleri.|  
|[double_3 sınıfı](double-3-class.md)|3 kısa bir vektör temsil eden `double` değerleri.|  
|[double_4 sınıfı](double-4-class.md)|4 kısa bir vektör temsil eden `double` değerleri.|  
|[float_2 sınıfı](float-2-class.md)|Kısa bir vektör 2 değerini temsil eden `float` değerleri.|  
|[float_3 sınıfı](float-3-class.md)|3 kısa bir vektör temsil eden `float` değerleri.|  
|[float_4 sınıfı](float-4-class.md)|4 kısa bir vektör temsil eden `float` değerleri.|  
|[int_2 sınıfı](int-2-class.md)|Kısa bir vektör 2 değerini temsil eden `int` değerleri.|  
|[int_3 sınıfı](int-3-class.md)|3 kısa bir vektör temsil eden `int` değerleri.|  
|[int_4 sınıfı](int-4-class.md)|4 kısa bir vektör temsil eden `int` değerleri.|  
|[norm_2 sınıfı](norm-2-class.md)|Kısa bir vektör 2 değerini temsil eden `norm` değerleri.|  
|[norm_3 sınıfı](norm-3-class.md)|3 kısa bir vektör temsil eden `norm` değerleri.|  
|[norm_4 sınıfı](norm-4-class.md)|4 kısa bir vektör temsil eden `norm` değerleri.|  
|[uint_2 sınıfı](uint-2-class.md)|Kısa bir vektör 2 değerini temsil eden `uint` değerleri.|  
|[uint_3 sınıfı](uint-3-class.md)|3 kısa bir vektör temsil eden `uint` değerleri.|  
|[uint_4 sınıfı](uint-4-class.md)|4 kısa bir vektör temsil eden `uint` değerleri.|  
|[unorm_2 sınıfı](unorm-2-class.md)|Kısa bir vektör 2 değerini temsil eden `unorm` değerleri.|  
|[unorm_3 sınıfı](unorm-3-class.md)|3 kısa bir vektör temsil eden `unorm` değerleri.|  
|[unorm_4 sınıfı](unorm-4-class.md)|4 kısa bir vektör temsil eden `unorm` değerleri.|  
|[sampler sınıfı](sampler-class.md)|Doku örnekleme için kullanılan örneği yapılandırmasını temsil eder.|  
|[short_vector yapısı](short-vector-structure.md)|Kısa bir vektör değerlerin temel bir uygulamasını sağlar.|  
|[short_vector_traits yapısı](short-vector-traits-structure.md)|İçin kısa bir vektör türünü ve uzunluğu alınmasını sağlar.|  
|[texture_view sınıfı](texture-view-class.md)|Okuma erişimi ve bir doku yazma erişimi sağlar.|  
  
### <a name="functions"></a>İşlevler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[kopyalama](concurrency-graphics-namespace-functions.md#copy)|Fazla Yüklendi. Kaynağı doku içeriğini hedef ana bilgisayar arabelleğe kopyalar.|  
|[copy_async](concurrency-graphics-namespace-functions.md#copy_async)|Fazla Yüklendi. Zaman uyumsuz olarak kaynak doku içeriğini hedef ana bilgisayar arabelleğe kopyalar.|  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp_graphics.h  
  
 **Namespace:** eşzamanlılık  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
