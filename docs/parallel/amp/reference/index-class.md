---
title: "index sınıfı | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AMP/index
- AMP/Concurrency::index::index
- AMP/Concurrency::index::rank
dev_langs: C++
helpviewer_keywords: index structure
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8a1c4213ee94c063a7dff2a5b2c5e156b0ee91a7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="index-class"></a>index Sınıfı
Tanımlayan bir *N*-boyutlu dizin pographics cpp amp.md.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
template <int _Rank>  
class index;  
```  
  
#### <a name="parameters"></a>Parametreler  
 `_Rank`  
 Derece veya dimensions sayısı.  
  
## <a name="members"></a>Üyeler  
  
### <a name="public-constructors"></a>Ortak Oluşturucular  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[Dizin Oluşturucu](#ctor)|Yeni bir örneğini başlatır `index` sınıfı.|  
  
### <a name="public-operators"></a>Ortak İşleçler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[--işleci](#operator--)|Azaltır her öğeye `index` nesnesi.|  
|[operator(mod) =](#operator_mod_eq)|Her bir öğe mod (Kalan) hesaplar `index` nesne bu öğe bir sayıyla ayrıldığında.|  
|[işleç * =](#operator_star_eq)|Her öğeye çarpar `index` bir sayıyla nesnesi.|  
|[/ = işleci](#operator_div_eq)|Her öğeye böler `index` bir sayıyla nesnesi.|  
|[index::operator\[\]](#operator_at)|Belirtilen dizindeki öğeyi döndürür.|  
|[operator ++](#operator_add_add)|Her öğeye artırır `index` nesnesi.|  
|[+= işleci](#operator_add_eq)|Her öğe, belirtilen sayı ekler `index` nesnesi.|  
|[işleç =](#operator_eq)|Belirtilen içeriğini kopyalar `index` bunu nesnesine.|  
|[-= işleci](#operator_-_eq)|Her öğe, belirtilen sayıdan çıkarır `index` nesnesi.|  

  
### <a name="public-constants"></a>Genel sabitler  
  
|Ad|Açıklama|  
|----------|-----------------|  
|[sıra sabiti](#rank)|Derecesini depolar `index` nesnesi.|  
  
## <a name="inheritance-hierarchy"></a>Devralma Hiyerarşisi  
 `index`  
  
## <a name="remarks"></a>Açıklamalar  
 `index` Yapısını temsil eden bir koordinat vektör *N* benzersiz bir konumu belirten Tamsayı bir *N*-boyutlu alanı. Vektör değerleri en önemli için en az önemli sıralanır. Kullanarak bileşenlerini değerlerini alabilir [işleç =](#operator_eq).  
  
## <a name="requirements"></a>Gereksinimler  
 **Başlık:** amp.h  
  
 **Namespace:** eşzamanlılık  


## <a name="index_ctor"></a>Dizin Oluşturucu
Dizin sınıfının yeni bir örneğini başlatır.

```  
index() restrict(amp,cpu);

index(
   const index<_Rank>& _Other
) restrict(amp,cpu);

explicit index(
   int _I
) restrict(amp,cpu);

index(
   int _I0,
   int _I1
) restrict(amp,cpu);

index(
   int _I0,
   int _I1,
   int _I2
) restrict(amp,cpu);

explicit index(
   const int _Array[_Rank]
) restrict(amp,cpu);
``` 

### <a name="parameters"></a>Parametreler

_Array  
Rank değerlerle tek boyutlu dizi.  
_LİSANS  
Tek boyutlu bir dizini dizin konumu.  
_I0  
En önemli boyutun uzunluğu.  
_I1  
İleri-için-çoğu-önemli boyutun uzunluğu.  
_I2  
En az önemli boyutun uzunluğu.  
_Other  
Yeni dizin nesnesi dayandığı bir dizin nesnesi.  

## <a name="operator--"></a>--işleci
Azaltır her öğeye dizin nesnesi.  
```  
index<_Rank>& operator--() restrict(amp,cpu);  

index operator--(
   int
) restrict(amp,cpu);
```  
### <a name="return-values"></a>Döndürülen değerler
Önek işleci, dizin nesnesi için (* Bu). Sonek işleci için yeni bir dizin nesnesi.

## <a name="operator_mod_eq"></a>operator(mod) =   
Bu öğe belirtilen sayıyla ayrıldığında her öğenin dizini nesnesindeki mod (Kalan) hesaplar.

```  
index<_Rank>& operator%=(
   int _Rhs
) restrict(cpu, amp);
```  
### <a name="parameters"></a>Parametreler
_Rhs modulus bulmak için göre bölüneceği sayısı.
Değer dizin nesnesi döndürür.

## <a name="operator_star_eq"></a>işleç * =   
Her bir öğesinde dizin nesnesi tarafından belirtilen değerle çarpar.
```
index<_Rank>& operator*=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler
_Rhs çarpılacağı sayısı.

## <a name="operator_div_eq"></a>/ = işleci 
Her bir öğesinde dizin nesnesi belirtilen sayıyı böler.

```
index<_Rank>& operator/=(
   int _Rhs
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>Parametreler
_Rhs numarası bölün.

## <a name="operator_at"></a>işleci\[\]  
Belirtilen konumdaki dizini bileşenini döndürür.

```
int operator[] (
   unsigned _Index
) const restrict(amp,cpu);

int& operator[] (
   unsigned _Index
) restrict(amp,cpu);
```

### <a name="parameters"></a>Parametreler
_Index 0 derecesini eksi 1 ile arasında bir tamsayı.

### <a name="return-value"></a>Dönüş Değeri
Belirtilen dizindeki öğeyi.

### <a name="remarks"></a>Açıklamalar
Bu aşağıdaki örnekte, dizin bileşeni değerlerini görüntüler.
```  
// Prints 1 2 3.
concurrency::index<3> idx(1, 2, 3);
std::cout << idx[0] << "\n";
std::cout << idx[1] << "\n";
std::cout << idx[2] << "\n";
```

## <a name="operator_add_add"></a>operator ++   
Her öğe Index nesnesinin artırır.
```  
index<_Rank>& operator++() restrict(amp,cpu);

index<_Rank> operator++(
   int
) restrict(amp,cpu);
```  
### <a name="return-value"></a>Dönüş Değeri
Önek işleci, dizin nesnesi için (* Bu). Sonek işleci için yeni bir dizin nesnesi.

## <a name="operator_add_eq"></a>+= işleci   
Belirtilen dizin nesnesi her öğesine ekler.
```  
index<_Rank>& operator+=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator+=(
   int _Rhs
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>Parametreler
_Rhs eklemek için sayısı.

### <a name="return-value"></a>Dönüş Değeri
Dizin nesnesi.

## <a name="operator_eq"></a>işleç =   
Belirtilen dizin nesnesi içeriğini bunu kopyalar.
```  
index<_Rank>& operator=(
   const index<_Rank>& _Other
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>Parametreler
_Other kopyalamak için dizin nesnesi.

### <a name="return-value"></a>Dönüş Değeri
Bu dizin nesneye başvuru.

## <a name="operator_-_eq"></a>-= işleci
Belirtilen dizin nesnesinin her öğeden çıkarır.
```  
index<_Rank>& operator-=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator-=(
   int _Rhs
) restrict(amp,cpu);
```  
### <a name="parameters"></a>Parametreler
_Rhs çıkartılacak sayı.

### <a name="return-value"></a>Dönüş Değeri
Dizin nesnesi.   

## <a name="rank"></a>RANK  
  Dizin nesnesi sırasını alır.
```
static const int rank = _Rank;
``` 
## <a name="see-also"></a>Ayrıca Bkz.  
 [Eşzamanlılık Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)
