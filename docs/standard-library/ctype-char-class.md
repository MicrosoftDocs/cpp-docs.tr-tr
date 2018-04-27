---
title: CType&lt;char&gt; sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- ctype<char>
- locale/std::ctype<char>
dev_langs:
- C++
helpviewer_keywords:
- ctype<char> class
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ae5ad9c448b7bbf4ad0fc2b0f831720ec3c059e8
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/26/2018
---
# <a name="ctypeltchargt-class"></a>CType&lt;char&gt; sınıfı

Bir şablon sınıfı açık alt uzmanlaşması sınıftır **ctype\<CharType**> yazmak için `char`, çeşitli özelliklerini bir karakter türü nitelemek için yerel ayar model hizmet verebilir nesneyi açıklayan `char`.

## <a name="syntax"></a>Sözdizimi

```cpp
template <>
class ctype<char>
: public ctype_base
{
public:
    typedef char _Elem;
    typedef _Elem char_type;
    bool is(
    mask _Maskval,
    _Elem _Ch) const;


    const _Elem* is(
    const _Elem* first,
    const _Elem* last,
    mask* dest) const;


    const _Elem* scan_is(
    mask _Maskval,
    const _Elem* first,
    const _Elem* last) const;


    const _Elem* scan_not(
    mask _Maskval,
    const _Elem* first,
    const _Elem* last) const;


    _Elem tolower(
    _Elem _Ch) const;


    const _Elem* tolower(
    _Elem* first,
    const _Elem* last) const;


    _Elem toupper(
    _Elem _Ch) const;


    const _Elem* toupper(
    _Elem* first,
    const _Elem* last) const;


    _Elem widen(
    char _Byte) const;


    const _Elem* widen(
    const char* first,
    const char* last,
    _Elem* dest) const;


    const _Elem* _Widen_s(
    const char* first,
    const char* last,
    _Elem* dest,
    size_t dest_size) const;


    _Elem narrow(
    _Elem _Ch,
    char _Dflt = '\0') const;


    const _Elem* narrow(
    const _Elem* first,
    const _Elem* last,
    char _Dflt,
    char* dest) const;


    const _Elem* _Narrow_s(
    const _Elem* first,
    const _Elem* last,
    char _Dflt,
    char* dest,
    size_t dest_size) const;


    static locale::id& id;
    explicit ctype(
    const mask* _Table = 0,
    bool _Deletetable = false,
    size_t _Refs = 0);

protected:
    virtual ~ctype();
//other protected members
};
```

## <a name="remarks"></a>Açıklamalar

Şablon sınıfı çeşitli şekillerde açık uzmanlık farklıdır:

- Bir nesne sınıfı ctype < `char`> ctype maskesini ilk öğesi, bir dizi UCHAR_MAX + 1 öğe türü için bir işaretçi depolar **ctype_base::mask**. Ayrıca bir dizinin silinmesi gerekip gerekmediğini gösteren bir Boole nesnesi depolar (kullanarak `operator delete[]`) olduğunda ctype\< **Elem**> Nesne yok.

- Tek genel kurucusu belirtmenize olanak sağlar. **sekmesini**, ctype maskesini ve **del**, dizi gerekiyorsa true Boolean nesnesi ne zaman silinmiş ctype < `char`> nesnesi yok , başvuru sayısı parametre refs yanı sıra.

- Korumalı üye fonksiyonu **tablo** saklı ctype maskesi tablo döndürür.

- Statik üye nesne **table_size** ctype maskesi tablosunda en az öğe sayısını belirtir.

- Korumalı statik üye fonksiyonu **classic_table**(ctype maskesi tablo uygun "C" yerel olarak döndürür.

- Korumalı sanal üye işlevleri vardır [do_is](../standard-library/ctype-class.md#do_is), [do_scan_is](../standard-library/ctype-class.md#do_scan_is), veya [do_scan_not](../standard-library/ctype-class.md#do_scan_not). Karşılık gelen ortak üye işlevleri eşdeğer işlemleri gerçekleştirir.

Üye işlevleri [do_narrow](../standard-library/ctype-class.md#do_narrow) ve [do_widen](../standard-library/ctype-class.md#do_widen) değiştirilmemiş öğeleri kopyalayın.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[facet sınıfı](http://msdn.microsoft.com/Library/dd4f12f5-cb1b-457f-af56-2fb204216ec1)<br/>
[ctype_base Sınıfı](../standard-library/ctype-base-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
