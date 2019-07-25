---
title: CType&lt;char&gt; sınıfı
ms.date: 11/04/2016
f1_keywords:
- ctype<char>
- locale/std::ctype<char>
helpviewer_keywords:
- ctype<char> class
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
ms.openlocfilehash: 7fe1eef32741d63e7b2e2c2320d18f445784c44f
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/24/2019
ms.locfileid: "68455463"
---
# <a name="ctypeltchargt-class"></a>CType&lt;char&gt; sınıfı

Sınıfı, Char türünde bir karakterin çeşitli özelliklerini niteleyen bir yerel ayar modeli olarak işlev görebilecek bir nesneyi açıklayan, `ctype\<CharType>` **char**yazmak için şablon sınıfının açık bir **özelleştirmesi.**

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

Açık özelleştirme, şablon sınıfından çeşitli yollarla farklılık gösterir:

- CType < `char`> sınıfının bir nesnesi bir CType maske tablosunun ilk öğesine bir işaretçi depolar, bu tür `ctype_base::mask`bir uchar_max + 1 öğelerinden oluşan bir dizi. Ayrıca, CType `operator delete[]`\< **eled**> nesnesi yok edildiğinde dizinin silinip silinmeyeceğini (kullanılarak) belirten bir Boole nesnesi de depolar.

- Tek genel Oluşturucusu, CType < `tab` `char`> nesnesi yok edildiğinde ve başvuru sayısının yanı `del`sıra, dize siliniyorsa, CType maske tablosu ve, Boolean nesnesini belirtmenize olanak tanır. parametre başvuruları.

- Protected member işlevi `table` , depolanan CType maske tablosunu döndürür.

- Statik üye nesnesi `table_size` bir CType maske tablosundaki en az öğe sayısını belirtir.

- Korunan statik üye işlevi `classic_table`("C" yerel ayarına uygun CType maske tablosunu döndürür.

- [Do_is](../standard-library/ctype-class.md#do_is), [do_scan_is](../standard-library/ctype-class.md#do_scan_is)veya [do_scan_not](../standard-library/ctype-class.md#do_scan_not)korumalı sanal üye işlevi yok. Karşılık gelen ortak üye işlevleri, denk işlemleri gerçekleştirir.

Üye işlevleri [do_narrow](../standard-library/ctype-class.md#do_narrow) ve [do_widen](../standard-library/ctype-class.md#do_widen) Copy öğeleri değiştirilmez.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:** \<yerel ayar >

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[model sınıfı](locale-class.md#facet_class)\
[ctype_base sınıfı](../standard-library/ctype-base-class.md)\
[C++ Standart Kitaplığında İş Parçacığı Güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
