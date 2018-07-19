---
title: CType&lt;char&gt; sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- ctype<char>
- locale/std::ctype<char>
dev_langs:
- C++
helpviewer_keywords:
- ctype<char> class
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 47ac9fa5431b5edfb4885dfdbf39be6c6b89cee6
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/11/2018
ms.locfileid: "38960667"
---
# <a name="ctypeltchargt-class"></a>CType&lt;char&gt; sınıfı

Şablon sınıfının açık uzmanlığı sınıftır `ctype\<CharType>` türüne **char**, türü bir karakterin çeşitli özelliklerini karakterize etmek için bir yerel ayar modeli hizmet verebilen bir nesneyi tanımlayan **char**.

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

Açık özelleştirme, Şablon sınıfı, çeşitli şekillerde farklıdır:

- Bir nesne sınıfı ctype < `char`> ctype maskesini ilk öğesi, bir dizi UCHAR_MAX + 1 öğesi türü için bir işaretçi depolayan `ctype_base::mask`. Ayrıca bir dizinin silinmesi gerekip gerekmediğini belirten bir Boolean nesnesi depolar (kullanarak `operator delete[]`) olduğunda ctype\< **Elem**> nesnesi yok edildiğinde.

- Tek bir Genel oluşturucu belirtmenize olanak tanır `tab`, ctype maskesini ve `del`, dizi olması gerekiyorsa true olan Boolean nesnesi ne zaman silinmiş ctype < `char`> nesnesi yok edildiğinde, başvuru sayısının yanı sıra parametre refs.

- Korumalı üye işlevi `table` saklı ctype maskesi tablosunu döndürür.

- Statik üye nesne `table_size` ctype maskesi tabloda öğeleri en az sayısını belirtir.

- Korumalı statik üye işlevi `classic_table`("C" yerel ayarına uygun olarak ctype maskesi tablosunu döndürür.

- Korumalı sanal üye işlev yok [do_is](../standard-library/ctype-class.md#do_is), [do_scan_is](../standard-library/ctype-class.md#do_scan_is), veya [do_scan_not](../standard-library/ctype-class.md#do_scan_not). Karşılık gelen ortak üye işlevleri eşdeğer işlemleri gerçekleştirin.

Üye işlevleri [do_narrow](../standard-library/ctype-class.md#do_narrow) ve [do_widen](../standard-library/ctype-class.md#do_widen) değiştirilmeden öğeleri kopyalama.

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<yerel ayar >

**Namespace:** std

## <a name="see-also"></a>Ayrıca bkz.

[facet sınıfı](http://msdn.microsoft.com/Library/dd4f12f5-cb1b-457f-af56-2fb204216ec1)<br/>
[ctype_base Sınıfı](../standard-library/ctype-base-class.md)<br/>
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
