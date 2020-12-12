---
description: 'Daha fazla bilgi edinin: CType &lt; char &gt; sınıfı'
title: CType &lt; char &gt; sınıfı
ms.date: 11/04/2016
f1_keywords:
- ctype<char>
- locale/std::ctype<char>
helpviewer_keywords:
- ctype<char> class
ms.assetid: ee30acb4-a743-405e-b3d4-13602092da84
ms.openlocfilehash: f423b66f75cc0e1ee823251977e7d048b3c19e02
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324674"
---
# <a name="ctypeltchargt-class"></a>CType &lt; char &gt; sınıfı

Sınıfı, türünde `ctype\<CharType>` **`char`** bir karakterin çeşitli özelliklerini niteleyen bir yerel ayar modeli olarak işlev görebilecek bir nesneyi açıklayan, bir sınıf şablonu türünün açık bir özelleştirmesi **`char`** .

## <a name="syntax"></a>Syntax

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

Açık özelleştirme, sınıf şablonundan çeşitli yollarla farklılık gösterir:

- Sınıfının bir nesnesi `ctype<char>` , bir CType maske tablosunun ilk öğesine bir işaretçi depolar, türü uchar_max + 1 öğelerinden oluşan bir dizi `ctype_base::mask` . Ayrıca `operator delete[]` , CType nesnesi yok edildiğinde dizinin silinip silinmeyeceğini (kullanılarak) belirten bir Boole nesnesi de depolar \< **Elem**> .

- Tek genel Oluşturucu `tab` , `del` nesne yok edildiğinde ve `ctype<char>` başvuru sayısı parametresi refs olan dize silinmeli, CType maske tablosu ve, Boolean nesnesini belirtmenize olanak tanır.

- Protected member işlevi, `table` depolanan CType maske tablosunu döndürür.

- Statik üye nesnesi `table_size` bir CType maske tablosundaki en az öğe sayısını belirtir.

- Korunan statik üye işlevi `classic_table` ("C" yerel ayarına uygun CType maske tablosunu döndürür.

- [Do_is](../standard-library/ctype-class.md#do_is), [do_scan_is](../standard-library/ctype-class.md#do_scan_is)veya [do_scan_not](../standard-library/ctype-class.md#do_scan_not)korunan sanal üye işlevleri yok. Karşılık gelen ortak üye işlevleri, denk işlemleri gerçekleştirir.

Üye işlevleri [do_narrow](../standard-library/ctype-class.md#do_narrow) ve [do_widen](../standard-library/ctype-class.md#do_widen) öğeleri değiştirilmemiş olarak kopyalar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<locale>

**Ad alanı:** std

## <a name="see-also"></a>Ayrıca bkz.

[model sınıfı](locale-class.md#facet_class)\
[ctype_base sınıfı](../standard-library/ctype-base-class.md)\
[C++ standart kitaplığı 'nda iş parçacığı güvenliği](../standard-library/thread-safety-in-the-cpp-standard-library.md)
