---
title: enable_shared_from_this sınıfı | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- memory/std::enable_shared_from_this
dev_langs:
- C++
helpviewer_keywords:
- enable_shared_from_this class
- enable_shared_from_this
ms.assetid: 9237603d-22e2-421f-b070-838ac006baf5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9bc34a0a176e39a30e6cdb5d4c2cdeeebc94b5b1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
---
# <a name="enablesharedfromthis-class"></a>enable_shared_from_this Sınıfı

Oluştur yardımcı olan bir `shared_ptr`.

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

`Ty` Paylaşılan işaretçiyi tarafından denetlenen türü.

## <a name="remarks"></a>Açıklamalar

Nesneleri türetilen `enable_shared_from_this` kullanabilirsiniz `shared_from_this` oluşturmak için üye işlevleri yöntemleri [shared_ptr](../standard-library/shared-ptr-class.md) var olan sahipliği paylaşan sahipleri örneğinin `shared_ptr` sahipleri. Aksi takdirde, yeni bir oluşturursanız `shared_ptr` kullanarak `this`, mevcut farklıdır `shared_ptr` başvuru geçersiz veya birden çok kez Silinecek nesnenin neden açabilir sahipleri.

Oluşturucular, yıkıcı ve atama işleci yanlışlıkla kötüye kullanımı önlemek için korunur. Şablon bağımsız değişken türü `Ty` türetilmiş sınıf türünde olmalıdır.

Kullanım örneği için bkz: [enable_shared_from_this::shared_from_this](#shared_from_this).

## <a name="requirements"></a>Gereksinimler

**Başlık:** \<bellek >

**Namespace:** std

## <a name="shared_from_this"></a>  enable_shared_from_this::shared_from_this

Oluşturan bir `shared_ptr` , var olan örnek sahipliğini paylaşır `shared_ptr` sahipleri.

```cpp
shared_ptr<T> shared_from_this();
shared_ptr<const T> shared_from_this() const;
```

### <a name="remarks"></a>Açıklamalar

Türetilen zaman nesnelerden `enable_shared_from_this` temel sınıfı, `shared_from_this` şablonu üye işlevlerini return bir [shared_ptr sınıfı](../standard-library/shared-ptr-class.md) var olan bu örneğinin sahipliğini paylaşır nesne `shared_ptr` sahipleri. Aksi takdirde, yeni bir oluşturursanız `shared_ptr` gelen `this`, mevcut farklıdır `shared_ptr` başvuru geçersiz veya birden çok kez Silinecek nesnenin neden açabilir sahipleri. Çağırırsanız davranış tanımsızdır `shared_from_this` zaten tarafından sahiplenilmedi bir örneğinde bir `shared_ptr` nesnesi.

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