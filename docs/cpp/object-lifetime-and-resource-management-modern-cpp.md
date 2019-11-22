---
title: Nesne yaşam süresi ve kaynak yönetimi (Çıı)
description: Kaynak sızıntılarını önlemek için modern C++ 'teki çii 'ın ilkesini izleyin.
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: 8aa0e1a1-e04d-46b1-acca-1d548490700f
ms.openlocfilehash: 01867ec0a71ba54bb6534da1b408cb0610d652a7
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303371"
---
# <a name="object-lifetime-and-resource-management-raii"></a>Nesne yaşam süresi ve kaynak yönetimi (Çıı)

Yönetilen dillerin aksine, C++ otomatik *atık toplama*yoktur. Bu, bir program çalışırken yığın belleği ve diğer kaynakları serbest bırakan bir iç işlemdir. Bir C++ program, tüm alınan kaynakların işletim sistemine döndürülmesinden sorumludur. Kullanılmayan bir kaynağı serbest bırakma hatası, *sızıntı*olarak adlandırılır. Sızan kaynaklar, işlem bitene kadar diğer programlar için kullanılamaz. Özellikle de bellek sızıntıları, C stili programlamada hataların yaygın nedenlidir.

Modern C++ nesneler, yığındaki nesneleri bildirerek, mümkün olduğunca yığın bellek kullanımını engeller. Bir kaynak, yığın için çok büyükse, bir nesnesine *ait* olmalıdır. Nesne başlatılırken, sahip olduğu kaynağı alır. Daha sonra nesne yıkıcısında kaynağı serbest bırakmaktan sorumludur. Sahip olan nesnenin kendisi yığında bildirilmiştir. *Nesnelerin sahip* olduğu ilke, "kaynak alımı başlatma" veya rayii olarak da bilinir.

Kaynak sahibi bir yığın nesnesi kapsam dışına geçtiğinde, yok edicisi otomatik olarak çağrılır. Bu şekilde, ' deki C++ çöp toplama, nesne ömrü ile yakından ilgilidir ve belirleyici olur. Bir kaynak, programda her zaman bilinen bir noktada serbest bırakılır ve bu, denetleyebilir. Yalnızca içindeki C++ gibi belirleyici Yıkıcılar belleği ve bellek olmayan kaynakları eşit şekilde işleyebilir.

Aşağıdaki örnek bir basit nesne `w`göstermektedir. İşlev kapsamındaki yığında bildirilmiştir ve işlev bloğunun sonunda yok edilir. Nesne `w` hiç *kaynak* (yığın olarak ayrılan bellek gibi) sahip değil. Tek üye `g` yığın üzerinde bildirilmiştir ve `w`ile birlikte kapsam dışına çıkar. `widget` yıkıcısında özel kod gerekmez.

```cpp
class widget {
private:
    gadget g;   // lifetime automatically tied to enclosing object
public:
    void draw();
};

void functionUsingWidget () {
    widget w;   // lifetime automatically tied to enclosing scope
                // constructs w, including the w.g gadget member
    // ...
    w.draw();
    // ...
} // automatic destruction and deallocation for w and w.g
  // automatic exception safety,
  // as if "finally { w.dispose(); w.g.dispose(); }"
```

Aşağıdaki örnekte, `w` bir bellek kaynağına sahiptir ve bu nedenle belleği silmek için yıkıcısında kodu olmalıdır.
 
```cpp
class widget
{
private:
    int* data;
public:
    widget(const int size) { data = new int[size]; } // acquire
    ~widget() { delete[] data; } // release
    void do_something() {}
};

void functionUsingWidget() {
    widget w(1000000);   // lifetime automatically tied to enclosing scope
                        // constructs w, including the w.data member
    w.do_something();

} // automatic destruction and deallocation for w and w.data

```

C++ 11 ' den beri, önceki örneği yazmanın daha iyi bir yolu vardır: Standart kitaplıktan akıllı bir işaretçi kullanarak. Akıllı işaretçi, sahip olduğu belleği ayırmayı ve silmeyi işler. Akıllı bir işaretçi kullanmak, `widget` sınıfında açık yıkıcı gereksinimini ortadan kaldırır.

```cpp
#include <memory>
class widget
{
private:
    std::unique_ptr<int> data;
public:
    widget(const int size) { data = std::make_unique<int>(size); }
    void do_something() {}
};

void functionUsingWidget() {
    widget w(1000000);   // lifetime automatically tied to enclosing scope
                // constructs w, including the w.data gadget member
    // ...
    w.do_something();
    // ...
} // automatic destruction and deallocation for w and w.data

```

Bellek ayırma için akıllı işaretçiler kullanarak bellek sızıntılarını ortadan kaldırabilirsiniz. Bu model, dosya tanıtıcıları veya yuvalar gibi diğer kaynaklar için geçerlidir. Sınıflarınızda benzer bir şekilde kendi kaynaklarınızı yönetebilirsiniz. Daha fazla bilgi için bkz. [akıllı işaretçiler](smart-pointers-modern-cpp.md).

Öğesinin C++ tasarımı, kapsam dışına çıktıklarında nesnelerin yok edilmesini sağlar. Diğer bir deyişle, bloklara çıkış olarak iptal edilir. Bir nesne yok edildiğinde, temelleri ve üyeleri belirli bir sırada yok edilir. Genel kapsamda herhangi bir bloğun dışında bildirildiği nesneler sorunlara yol açabilir. Genel bir nesnenin Oluşturucusu bir özel durum oluşturursa hata ayıklaması zor olabilir.

## <a name="see-also"></a>Ayrıca bkz.

[Uygulamasına geri hoş geldinizC++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ Dil Başvurusu](../cpp/cpp-language-reference.md)<br/>
[C++ Standart Kitaplığı](../standard-library/cpp-standard-library-reference.md)
