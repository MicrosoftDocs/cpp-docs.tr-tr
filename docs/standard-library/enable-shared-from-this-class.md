---
title: enable_shared_from_this Sınıfı
ms.date: 11/04/2016
f1_keywords:
- memory/std::enable_shared_from_this
helpviewer_keywords:
- enable_shared_from_this class
- enable_shared_from_this
ms.assetid: 9237603d-22e2-421f-b070-838ac006baf5
ms.openlocfilehash: 9bf5055aefe505461e81703373ecb042a1f7224a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50547829"
---
# <a name="enablesharedfromthis-class"></a>enable_shared_from_this Sınıfı

Üretmeye yardımcı olur bir `shared_ptr`.

## <a name="syntax"></a>Sözdizimi

```cpp
class enable_shared_from_this {
public:
    shared_ptr<Ty>
        shared_from_this();
    shared_ptr<const Ty> shared_from_this() const;
protected:
    enable_shared_from_this();
    enable_shared_from_this(const enable_shared_from_this&);
    enable_shared_from_this& operator=(const enable_shared_from_this&);
    ~enable_shared_from_this();
};
```

### <a name="parameters"></a>Parametreler

*Ty*<br/>
Paylaşılan işaretçiyle kontrol edilen tür.

## <a name="remarks"></a>Açıklamalar

Türetilmiş nesneler `enable_shared_from_this` kullanabilirsiniz `shared_from_this` üye işlevleri oluşturmak için yöntemleri [shared_ptr](../standard-library/shared-ptr-class.md) bu paylaşım sahipliğinin var olan örneğinin sahipleri `shared_ptr` sahipler. Aksi takdirde, yeni bir oluşturursanız `shared_ptr` kullanarak **bu**, varolan farklıdır `shared_ptr` sahiplerinin, başvuru geçersiz veya birden çok kez silinmesine neden neden olabilir.

Oluşturucular, yok edici ve atama işleci, yanlışlıkla kötüye kullanımı önlemek için korunur. Şablon bağımsız değişken türü *Ty* türetilmiş sınıf türünde olmalıdır.

Kullanım örneği için bkz: [enable_shared_from_this::shared_from_this](#shared_from_this).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<bellek >

**Namespace:** std

## <a name="shared_from_this"></a>  enable_shared_from_this::shared_from_this

Oluşturur bir `shared_ptr` , var olan örneğinin sahipliği paylaşır `shared_ptr` sahipler.

```cpp
shared_ptr<T> shared_from_this();
shared_ptr<const T> shared_from_this() const;
```

### <a name="remarks"></a>Açıklamalar

Nesnelerden türetilmesi zaman `enable_shared_from_this` temel sınıfı, `shared_from_this` şablon üye işlev dönüş bir [shared_ptr sınıfı](../standard-library/shared-ptr-class.md) var olan bu örneği sahipliğini paylaşan nesne `shared_ptr` sahipler. Aksi takdirde, yeni bir oluşturursanız `shared_ptr` gelen **bu**, varolan farklıdır `shared_ptr` sahiplerinin, başvuru geçersiz veya birden çok kez silinmesine neden neden olabilir. Çağırırsanız davranış tanımlanmamıştır `shared_from_this` zaten sahibi olmayan bir örneği üzerinde bir `shared_ptr` nesne.

### <a name="example"></a>Örnek

```cpp
// std_memory_shared_from_this.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

using namespace std;

struct base : public std::enable_shared_from_this<base>
{
    int val;
    shared_ptr<base> share_more()
    {
        return shared_from_this();
    }
};

int main()
{
    auto sp1 = make_shared<base>();
    auto sp2 = sp1->share_more();

    sp1->val = 3;
    cout << "sp2->val == " << sp2->val << endl;
    return 0;
}
```

```Output
sp2->val == 3
```

## <a name="see-also"></a>Ayrıca bkz.

[enable_shared_from_this::shared_from_this](#shared_from_this)<br/>
[shared_ptr Sınıfı](../standard-library/shared-ptr-class.md)<br/>