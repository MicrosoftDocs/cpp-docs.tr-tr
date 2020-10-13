---
title: 'Nasıl yapılır: taşıma oluşturucularını ve taşıma atama işleçlerini tanımlama (C++)'
ms.date: 03/05/2018
helpviewer_keywords:
- move constructor [C++]
ms.assetid: e75efe0e-4b74-47a9-96ed-4e83cfc4378d
ms.openlocfilehash: e57f67eeca93572b26ee03033cbe4dcf90431f78
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008872"
---
# <a name="move-constructors-and-move-assignment-operators-c"></a>Taşıma Oluşturucuları ve Taşıma Atama İşleçleri (C++)

Bu konu, bir C++ sınıfı için bir *taşıma oluşturucusunun* ve taşıma atama işlecinin nasıl yazılacağını açıklar. Bir taşıma Oluşturucusu, bir rvalue nesnesine ait kaynakların kopyalamadan bir lvalue 'ye taşınmasını sağlar. Taşıma semantiği hakkında daha fazla bilgi için bkz. [rvalue başvuru bildirimci:  &&](../cpp/rvalue-reference-declarator-amp-amp.md).

Bu konu, `MemoryBlock` bir bellek arabelleğini yöneten aşağıdaki C++ sınıfı üzerinde oluşturulur.

```cpp
// MemoryBlock.h
#pragma once
#include <iostream>
#include <algorithm>

class MemoryBlock
{
public:

   // Simple constructor that initializes the resource.
   explicit MemoryBlock(size_t length)
      : _length(length)
      , _data(new int[length])
   {
      std::cout << "In MemoryBlock(size_t). length = "
                << _length << "." << std::endl;
   }

   // Destructor.
   ~MemoryBlock()
   {
      std::cout << "In ~MemoryBlock(). length = "
                << _length << ".";

      if (_data != nullptr)
      {
         std::cout << " Deleting resource.";
         // Delete the resource.
         delete[] _data;
      }

      std::cout << std::endl;
   }

   // Copy constructor.
   MemoryBlock(const MemoryBlock& other)
      : _length(other._length)
      , _data(new int[other._length])
   {
      std::cout << "In MemoryBlock(const MemoryBlock&). length = "
                << other._length << ". Copying resource." << std::endl;

      std::copy(other._data, other._data + _length, _data);
   }

   // Copy assignment operator.
   MemoryBlock& operator=(const MemoryBlock& other)
   {
      std::cout << "In operator=(const MemoryBlock&). length = "
                << other._length << ". Copying resource." << std::endl;

      if (this != &other)
      {
         // Free the existing resource.
         delete[] _data;

         _length = other._length;
         _data = new int[_length];
         std::copy(other._data, other._data + _length, _data);
      }
      return *this;
   }

   // Retrieves the length of the data resource.
   size_t Length() const
   {
      return _length;
   }

private:
   size_t _length; // The length of the resource.
   int* _data; // The resource.
};
```

Aşağıdaki yordamlarda, örnek C++ sınıfı için bir taşıma oluşturucusunun ve taşıma atama işlecinin nasıl yazılacağı açıklanır.

### <a name="to-create-a-move-constructor-for-a-c-class"></a>C++ sınıfı için bir taşıma Oluşturucusu oluşturmak için

1. Aşağıdaki örnekte gösterildiği gibi, sınıf türüne parametre olarak bir rvalue başvurusu alan boş bir Oluşturucu yöntemi tanımlayın:

    ```cpp
    MemoryBlock(MemoryBlock&& other)
       : _data(nullptr)
       , _length(0)
    {
    }
    ```

1. Taşıma oluşturucusunda, kaynak nesnesinden sınıf veri üyelerini oluşturulmakta olan nesneye atayın:

    ```cpp
    _data = other._data;
    _length = other._length;
    ```

1. Kaynak nesnenin veri üyelerini varsayılan değerlere atayın. Bu, yıkıcının kaynakları (örneğin, bellek) birden çok kez boşaltmasını önler:

    ```cpp
    other._data = nullptr;
    other._length = 0;
    ```

### <a name="to-create-a-move-assignment-operator-for-a-c-class"></a>C++ sınıfı için bir taşıma atama işleci oluşturmak için

1. Sınıf türüne parametre olarak bir rvalue başvurusu alan ve aşağıdaki örnekte gösterildiği gibi sınıf türüne bir başvuru döndüren boş bir atama işleci tanımlayın:

    ```cpp
    MemoryBlock& operator=(MemoryBlock&& other)
    {
    }
    ```

1. Taşıma atama işlecinde, nesneyi kendine atamaya çalışırsanız hiçbir işlem gerçekleştiren bir koşullu ifade ekleyin.

    ```cpp
    if (this != &other)
    {
    }
    ```

1. Koşullu bildirimde, atanmakta olan nesneden tüm kaynakları (örneğin, bellek) boşaltın.

   Aşağıdaki örnek, `_data` atanan nesneden üyeyi serbest bırakır:

    ```cpp
    // Free the existing resource.
    delete[] _data;
    ```

   Veri üyelerini kaynak nesnesinden oluşturulmakta olan nesneye aktarmak için ilk yordamda 2. ve 3. adımları izleyin:

    ```cpp
    // Copy the data pointer and its length from the
    // source object.
    _data = other._data;
    _length = other._length;

    // Release the data pointer from the source object so that
    // the destructor does not free the memory multiple times.
    other._data = nullptr;
    other._length = 0;
    ```

1. Aşağıdaki örnekte gösterildiği gibi geçerli nesneye bir başvuru döndürün:

    ```cpp
    return *this;
    ```

## <a name="example-complete-move-constructor-and-assignment-operator"></a>Örnek: Move yapıcısı ve atama işleci

Aşağıdaki örnek, sınıfı için tüm taşıma oluşturucusunu ve taşıma atama işlecini gösterir `MemoryBlock` :

```cpp
// Move constructor.
MemoryBlock(MemoryBlock&& other) noexcept
   : _data(nullptr)
   , _length(0)
{
   std::cout << "In MemoryBlock(MemoryBlock&&). length = "
             << other._length << ". Moving resource." << std::endl;

   // Copy the data pointer and its length from the
   // source object.
   _data = other._data;
   _length = other._length;

   // Release the data pointer from the source object so that
   // the destructor does not free the memory multiple times.
   other._data = nullptr;
   other._length = 0;
}

// Move assignment operator.
MemoryBlock& operator=(MemoryBlock&& other) noexcept
{
   std::cout << "In operator=(MemoryBlock&&). length = "
             << other._length << "." << std::endl;

   if (this != &other)
   {
      // Free the existing resource.
      delete[] _data;

      // Copy the data pointer and its length from the
      // source object.
      _data = other._data;
      _length = other._length;

      // Release the data pointer from the source object so that
      // the destructor does not free the memory multiple times.
      other._data = nullptr;
      other._length = 0;
   }
   return *this;
}
```

## <a name="example-use-move-semantics-to-improve-performance"></a>Örnek performansı artırmak için taşıma semantiğini kullanın

Aşağıdaki örnek, taşıma semantiğinin uygulamalarınızın performansını nasıl geliştirebileceğinizi gösterir. Örnek, bir vektör nesnesine iki öğe ekler ve sonra varolan iki öğe arasında yeni bir öğe ekler. `vector`Sınıfı, vektör öğelerini kopyalamak yerine vektör öğelerinin taşıyarak ekleme işlemini verimli bir şekilde gerçekleştirmek için taşıma semantiğini kullanır.

```cpp
// rvalue-references-move-semantics.cpp
// compile with: /EHsc
#include "MemoryBlock.h"
#include <vector>

using namespace std;

int main()
{
   // Create a vector object and add a few elements to it.
   vector<MemoryBlock> v;
   v.push_back(MemoryBlock(25));
   v.push_back(MemoryBlock(75));

   // Insert a new element into the second position of the vector.
   v.insert(v.begin() + 1, MemoryBlock(50));
}
```

Bu örnek aşağıdaki çıktıyı üretir:

```Output
In MemoryBlock(size_t). length = 25.
In MemoryBlock(MemoryBlock&&). length = 25. Moving resource.
In ~MemoryBlock(). length = 0.
In MemoryBlock(size_t). length = 75.
In MemoryBlock(MemoryBlock&&). length = 75. Moving resource.
In MemoryBlock(MemoryBlock&&). length = 25. Moving resource.
In ~MemoryBlock(). length = 0.
In ~MemoryBlock(). length = 0.
In MemoryBlock(size_t). length = 50.
In MemoryBlock(MemoryBlock&&). length = 50. Moving resource.
In MemoryBlock(MemoryBlock&&). length = 25. Moving resource.
In MemoryBlock(MemoryBlock&&). length = 75. Moving resource.
In ~MemoryBlock(). length = 0.
In ~MemoryBlock(). length = 0.
In ~MemoryBlock(). length = 0.
In ~MemoryBlock(). length = 25. Deleting resource.
In ~MemoryBlock(). length = 50. Deleting resource.
In ~MemoryBlock(). length = 75. Deleting resource.
```

Visual Studio 2010 ' den önce Bu örnek aşağıdaki çıktıyı üreten:

```Output
In MemoryBlock(size_t). length = 25.
In MemoryBlock(const MemoryBlock&). length = 25. Copying resource.
In ~MemoryBlock(). length = 25. Deleting resource.
In MemoryBlock(size_t). length = 75.
In MemoryBlock(const MemoryBlock&). length = 25. Copying resource.
In ~MemoryBlock(). length = 25. Deleting resource.
In MemoryBlock(const MemoryBlock&). length = 75. Copying resource.
In ~MemoryBlock(). length = 75. Deleting resource.
In MemoryBlock(size_t). length = 50.
In MemoryBlock(const MemoryBlock&). length = 50. Copying resource.
In MemoryBlock(const MemoryBlock&). length = 50. Copying resource.
In operator=(const MemoryBlock&). length = 75. Copying resource.
In operator=(const MemoryBlock&). length = 50. Copying resource.
In ~MemoryBlock(). length = 50. Deleting resource.
In ~MemoryBlock(). length = 50. Deleting resource.
In ~MemoryBlock(). length = 25. Deleting resource.
In ~MemoryBlock(). length = 50. Deleting resource.
In ~MemoryBlock(). length = 75. Deleting resource.
```

Bu örneğin taşıma semantiğini kullanan sürümü, daha az kopya, bellek ayırma ve bellek ayırmayı kaldırma işlemleri gerçekleştirdiğinden, taşıma semantiğini kullanmayan sürümden daha verimlidir.

## <a name="robust-programming"></a>Güçlü Programlama

Kaynak sızıntılarını engellemek için, taşıma atama işlecinde her zaman (bellek, dosya tutamaçları ve yuvalar gibi) kaynakları boşaltın.

Kaynakların kurtarılamaz yok edilmesini engellemek için taşıma atama işlecinde kendi kendine atamayı doğru bir şekilde işleyin.

Sınıfınız için hem bir taşıma Oluşturucusu hem de bir taşıma ataması operatörü sağlarsanız, taşıma atamasını çağırmak için taşıma oluşturucusunu yazarak gereksiz kodu kaldırabilirsiniz. Aşağıdaki örnek, taşıma atama işlecini çağıran taşıma oluşturucusunun düzeltilmiş bir sürümünü göstermektedir:

```cpp
// Move constructor.
MemoryBlock(MemoryBlock&& other) noexcept
   : _data(nullptr)
   , _length(0)
{
   *this = std::move(other);
}
```

[Std:: Move](../standard-library/utility-functions.md#move) işlevi, lvalue değerini `other` rvalue değerine dönüştürür.

## <a name="see-also"></a>Ayrıca bkz.

[Rvalue Başvuru Bildirimcisi: &&](../cpp/rvalue-reference-declarator-amp-amp.md)<br/>
[std:: Move](../standard-library/utility-functions.md#move)
