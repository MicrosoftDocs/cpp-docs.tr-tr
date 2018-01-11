---
title: "Extent sınıfı (C++ AMP) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- extent
- AMP/extent
- AMP/Concurrency::extent::extent
- AMP/Concurrency::extent::contains
- AMP/Concurrency::extent::size
- AMP/Concurrency::extent::tile
- AMP/Concurrency::extent::rank Constant
dev_langs: C++
helpviewer_keywords: extent structure
ms.assetid: edb5de3d-3935-4dbb-8365-4cc6c4fb0269
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f93bcd69a6f0b05f9566fe3a2ffb6025729b63de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="extent-class-c-amp"></a>extent Sınıfı (C++ AMP)
Bir vektör temsil eden *N* sınırlarına belirten Tamsayı değerleri bir *N*-0 olan bir kaynağı sahip boyutlu alanı. Vektör değerleri en önemli için en az önemli sıralanır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
template <int _Rank>  
class extent;  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rank`  
 Derecesini `extent` nesnesi.  

 ## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp.h  
  
 **Namespace:** eşzamanlılık  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Uzantı Oluşturucusu](#ctor)|Yeni bir örneğini başlatır `extent` sınıfı.|  
  
### <a name="public-methods"></a>Ortak Yöntemler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[içerir](#contains)|Doğrular belirtilen `extent` nesnesi belirtilen derecesini sahiptir.|  
|[boyutu](#size)|Kapsam (birimlerindeki öğelerin) toplam doğrusal boyutu döndürür.|  
|[Döşeme](#tile)|Üreten bir `tiled_extent` nesnesi tarafından verilen döşeme kapsam ile belirtilen boyutları.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[operator-](#operator_min)|Yeni bir döndürür `extent` çıkarılmasıyla oluşturulan nesne `index` karşılık gelen gelen öğeleri `extent` öğeleri.|  
|[--işleci](#operator_min_min)|Azaltır her öğeye `extent` nesnesi.|  
|[operator % =](#operator_mod_eq)|Her bir öğe mod (Kalan) hesaplar `extent` nesne bu öğe bir sayıyla ayrıldığında.|  
|[işleç * =](#operator_star_eq)|Her öğeye çarpar `extent` bir sayıyla nesnesi.|  
|[/ = işleci](#operator_min_eq)|Her öğeye böler `extent` bir sayıyla nesnesi.|  
|[Extent::operator\[\]](#operator_at)|Belirtilen dizindeki öğeyi döndürür.|  
|[operator +](#operator_add)|Yeni bir döndürür `extent` karşılık gelen ekleyerek oluşturulan nesne `index` ve `extent` öğeleri.|  
|[operator ++](#operator_add_add)|Her öğeye artırır `extent` nesnesi.|  
|[+= işleci](#operator_add_eq)|Her öğe, belirtilen sayı ekler `extent` nesnesi.|  
|[işleç =](#operator_eq)|Başka bir içeriğini kopyalar `extent` bunu nesnesine.|  
|[-= işleci](#operator_min_eq)|Her öğe, belirtilen sayıdan çıkarır `extent` nesnesi.|  

  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[sıra sabiti](#rank)|Derecesini alır `extent` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `extent`  


## <a name="contains"></a>içerir 

Gösterir olup belirtilen [dizin](index-class.md) değeri 'kapsam' nesnesi içinde bulunan.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
bool contains(const index<rank>& _Index) const restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Index`  
 `index` Test etmek için değer.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `true`varsa belirtilen `index` değeri bulunduğu `extent` nesne; Aksi halde, `false`.  
  
##  <a name="ctor"></a>Kapsam 

'Kapsam' sınıfının yeni bir örneğini başlatır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
extent() restrict(amp,cpu);    
extent(const extent<_Rank>& _Other) restrict(amp,cpu);    
explicit extent(int _I) restrict(amp,cpu);    
extent(int _I0,  int _I1) restrict(amp,cpu);    
extent(int _I0,  int _I1, int _I2) restrict(amp,cpu);    
explicit extent(const int _Array[_Rank])restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Array`  
 Bir dizi `_Rank` yeni oluşturmak için kullanılan tamsayılar `extent` nesnesi.  
  
 `_I`  
 Uzantı uzunluğu.  
  
 `_I0`  
 En önemli boyutun uzunluğu.  
  
 `_I1`  
 İleri-için-çoğu-önemli boyutun uzunluğu.  
  
 `_I2`  
 En az önemli boyutun uzunluğu.  
  
 `_Other`  
 Bir `extent` nesne yeni `extent` nesne dayanır.  
  
## <a name="remarks"></a>Açıklamalar  
 Parametresiz bir kurucusu başlatır bir `extent` , üç derecesini sahip bir nesne.  
  
 Bir dizi oluşturmak için kullanılan bir `extent` nesnesi, dizi uzunluğu, derecesini eşleşmelidir `extent` nesnesi.  
  
##  <a name="operator_mod_eq"></a>operator % = 

Bu öğe bir sayıyla ayrıldığında her bir öğesinde 'kapsam' mod (Kalan) hesaplar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
extent<_Rank>& operator%=(int _Rhs) restrict(cpu, direct3d);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rhs`  
 Mod bulunacak sayı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `extent` Nesnesi.  
  
##  <a name="operator_star_eq"></a>işleç * = 

Her bir öğesinde 'kapsam' nesnesi tarafından belirtilen değerle çarpar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
extent<_Rank>& operator*=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rhs`  
 Çarp numarası.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `extent` Nesnesi.  
  
## <a name="operator_add"></a>operator + 

Yeni bir döndürür `extent` karşılık gelen ekleyerek oluşturulan nesne `index` ve `extent` öğeleri.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
extent<_Rank> operator+(const index<_Rank>& _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rhs`  
 `index` Eklemek için öğeleri içeren nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni `extent` nesnesi.  
  
##  <a name="operator_add_add"></a>operator ++ 

Her öğe 'kapsam' nesnesinin artırır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
extent<_Rank>& operator++() restrict(amp,cpu);    
extent<_Rank> operator++(int)restrict(amp,cpu);  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Önek işleci için `extent` nesne (`*this`). Sonek işleci için yeni bir `extent` nesnesi.  
  
##  <a name="operator_add_eq"></a>+= işleci 

Belirtilen sayı 'kapsam' nesnenin her bir öğesine ekler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
extent<_Rank>& operator+=(const extent<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator+=(const index<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator+=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rhs`  
 Sayı, dizin veya uzantı eklemek için.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Elde edilen `extent` nesnesi.  
  
##  <a name="operator_min"></a>operator- 

Yeni bir `extent` belirtilen her bir öğesinde çıkarılmasıyla nesne `index` karşılık gelen öğe bu nesneden `extent` nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
extent<_Rank> operator-(const index<_Rank>& _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rhs`  
 `index` Çıkartılacak öğeleri içeren nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Yeni `extent` nesnesi.  
  
##  <a name="operator_min_min"></a>--işleci 

Azaltır her bir öğesinde 'kapsam' nesnesi.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
extent<_Rank>& operator--() restrict(amp,cpu);    
extent<_Rank> operator--(int)restrict(amp,cpu);  
```  
  
### <a name="return-value"></a>Dönüş Değeri  
 Önek işleci için `extent` nesne (`*this`). Sonek işleci için yeni bir `extent` nesnesi.  
  
##  <a name="operator_div_eq"></a>/ = işleci 

Her bir öğesinde 'kapsam' nesnesi belirtilen sayıyı böler.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
extent<_Rank>& operator/=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rhs`  
 Bölün numarası.  
  
### <a name="return-value"></a>Dönüş Değeri  
 `extent` Nesnesi.  
  
##  <a name="operator_min_eq"></a>-= işleci 

Her öğe 'kapsam' nesnesinin belirtilen sayıdan çıkarır.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
extent<_Rank>& operator-=(const extent<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator-=(const index<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator-=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Rhs`  
 Çıkartılacak sayı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Elde edilen `extent` nesnesi.  
  
##  <a name="operator_eq"></a>işleç = 

Başka bir 'kapsam' nesnesinin içeriğini bunu kopyalar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
extent<_Rank>& operator=(const extent<_Rank>& _Other) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Other`  
 `extent` Kopyalanacak nesne.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Bu başvuru `extent` nesnesi.  
  
##  <a name="operator_at"></a>Extent::operator\[\] 
Belirtilen dizindeki öğeyi döndürür.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
int operator[](unsigned int _Index) const restrict(amp,cpu);    
int& operator[](unsigned int _Index) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Parametreler  
 `_Index`  
 0 derecesini eksi 1 ile arasında bir tamsayı.  
  
### <a name="return-value"></a>Dönüş Değeri  
 Belirtilen dizindeki öğeyi.  
  
##  <a name="rank_constant"></a>RANK 

Rank 'kapsam' nesnesinin depolar.  
  
### <a name="syntax"></a>Sözdizimi  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="size"></a>boyutu 

Toplam doğrusal boyutu döndüren `extent` nesnesinde (öğeleri birimleri).  
  
### <a name="syntax"></a>Sözdizimi  

```  
unsigned int size() const restrict(amp,cpu);  
```  
  
## <a name="tile"></a>Döşeme 

Belirtilen döşeme boyutlarla tiled_extent nesnesi oluşturur.

```
template <int _Dim0>
tiled_extent<_Dim0> tile() const ;

template <int _Dim0, int _Dim1>
tiled_extent<_Dim0, _Dim1> tile() const ;

template <int _Dim0, int _Dim1, int _Dim2>
tiled_extent<_Dim0, _Dim1, _Dim2> tile() const ;
```  
### <a name="parameters"></a>Parametreler
`_Dim0`Döşeli ölçüde en önemli bileşenidir.
`_Dim1`Döşeli ölçüde İleri-için-çoğu-önemli bileşenidir.
`_Dim2`Döşeli ölçüde en az önemli bileşenidir.


  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Ad Alanı (C++ AMP)](concurrency-namespace-cpp-amp.md)
