---
title: enable_shared_from_this Sınıfı
ms.date: 11/04/2016
f1_keywords:
- memory/std::enable_shared_from_this
helpviewer_keywords:
- enable_shared_from_this class
- enable_shared_from_this
ms.assetid: 9237603d-22e2-421f-b070-838ac006baf5
ms.openlocfilehash: 9b417eabdaf6002724a0fa947dd97dea6f0df0a5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217785"
---
# <a name="enable_shared_from_this-class"></a>enable_shared_from_this Sınıfı

Bir oluşturulmasına yardımcı olur `shared_ptr` .

## <a name="syntax"></a>Söz dizimi

```cpp
class enable_shared_from_this {
public:
    shared_ptr<Ty>
        shared_from_this();
    shared_ptr<const Ty> shared_from_this() const;
    weak_ptr<T> weak_from_this() noexcept;
    weak_ptr<T const> weak_from_this() const noexcept;
protected:
    enable_shared_from_this();
    enable_shared_from_this(const enable_shared_from_this&);
    enable_shared_from_this& operator=(const enable_shared_from_this&);
    ~enable_shared_from_this();
};
```

### <a name="parameters"></a>Parametreler

*Kalite*\
Paylaşılan işaretçi tarafından denetlenen tür.

## <a name="remarks"></a>Açıklamalar

Öğesinden türetilen nesneler, `enable_shared_from_this` var olan `shared_from_this` sahiplerin sahipliğini paylaşan örnek [shared_ptr](../standard-library/shared-ptr-class.md) sahiplerini oluşturmak için üye işlevlerindeki yöntemleri kullanabilir `shared_ptr` . Aksi takdirde, kullanarak yeni bir oluşturursanız `shared_ptr` **`this`** , bu, var olan `shared_ptr` sahiplerden farklıdır, bu da geçersiz başvurulara yol açabilir veya nesnenin birden çok kez silinmesine neden olabilir.

Oluşturucular, yıkıcı ve atama işleci yanlışlıkla kötüye kullanımı önlemeye yardımcı olmak için korunur. Şablon bağımsız *değişken türü, türetilmiş sınıfın türü olmalıdır* .

Kullanım örneği için bkz. [enable_shared_from_this:: shared_from_this](#shared_from_this).

## <a name="shared_from_this"></a><a name="shared_from_this"></a>shared_from_this

`shared_ptr`Örneği, var olan sahiplerin sahipliğini paylaşan bir oluşturur `shared_ptr` .

```cpp
shared_ptr<T> shared_from_this();
shared_ptr<const T> shared_from_this() const;
```

### <a name="remarks"></a>Açıklamalar

Temel sınıftan nesneler türettiğinizde `enable_shared_from_this` , `shared_from_this` şablon üye işlevleri bu örneğin sahipliğini var olan sahiplerle paylaşan bir [shared_ptr sınıf](../standard-library/shared-ptr-class.md) nesnesi döndürür `shared_ptr` . Aksi takdirde, öğesinden yeni bir oluşturursanız `shared_ptr` , **`this`** Bu, var olan `shared_ptr` sahiplerden farklıdır, bu da geçersiz başvurulara yol açabilir veya nesnenin birden çok kez silinmesine neden olabilir. `shared_from_this`Bir nesneye ait olmayan bir örneğe çağrı yaparsanız davranış tanımsızdır `shared_ptr` .

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

## <a name="weak_from_this"></a><a name="weak_from_this"></a>weak_from_this

```cpp
weak_ptr<T> weak_from_this() noexcept;
weak_ptr<T const> weak_from_this() const noexcept;
```
