---
title: 'Nasıl yapılır: taşıma oluşturucuları ve taşıma atama işleçleri (C++) tanımlama | Microsoft Docs'
ms.custom: ''
ms.date: 03/05/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-language
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- move constructor [C++]
ms.assetid: e75efe0e-4b74-47a9-96ed-4e83cfc4378d
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8bc9ce3d397b96ec45a0dbee5fefdb09d01b3f28
ms.sourcegitcommit: 770f6c4a57200aaa9e8ac6e08a3631a4b4bdca05
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/16/2018
---
# <a name="move-constructors-and-move-assignment-operators-c"></a>Taşıma Oluşturucuları ve Taşıma Atama İşleçleri (C++)
Bu konuda nasıl yazılacağını açıklar bir *taşıma Oluşturucusu* ve C++ sınıf için bir taşıma atama işleci. Bir taşıma oluşturucusuna kopyalamadan bir lvalue taşınacak rvalue nesne tarafından sahip olunan kaynaklar sağlar. Taşıma semantiği hakkında daha fazla bilgi için bkz: [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
 Bu konuda aşağıdaki C++ sınıfı derlemeler `MemoryBlock`, bellek arabelleği yönetir.  
  
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
  
 Aşağıdaki yordamlar, bir taşıma oluşturucusuna ve taşıma atama işleci C++ sınıfı örneği için yazılacak açıklar.  
  
### <a name="to-create-a-move-constructor-for-a-c-class"></a>Bir C++ sınıf için bir taşıma oluşturucusuna oluşturmak için  
  
1.  Rvalue başvuru sınıf türü için kendi parametre olarak alır bir boş Oluşturucusu yöntemi, aşağıdaki örnekte gösterildiği gibi tanımlayın:  
  
    ```cpp  
    MemoryBlock(MemoryBlock&& other)  
       : _data(nullptr)  
       , _length(0)  
    {  
    }  
    ```  
  
2.  Taşıma oluşturucuda sınıf veri üyeleri kaynak nesneden oluşturulmuyor nesnesine atayın:  
  
    ```cpp  
    _data = other._data;  
    _length = other._length;  
    ```  
  
3.  Kaynak nesne veri üyeleri için varsayılan değerler atayın. Bu, yıkıcı kaynakları (örneğin bellek) birden çok kez boşaltmasını engeller:  
  
    ```cpp  
    other._data = nullptr;  
    other._length = 0;  
    ```  
  
### <a name="to-create-a-move-assignment-operator-for-a-c-class"></a>Bir C++ sınıf için bir taşıma atama işleci oluşturmak için  

1.  Rvalue başvuru sınıf türü, parametre olarak alıp bir başvuru sınıf türü döndüren bir boş atama işleci, aşağıdaki örnekte gösterildiği gibi tanımlayın:  
  
    ```cpp  
    MemoryBlock& operator=(MemoryBlock&& other)  
    {  
    }  
    ```  
  
2.  Taşıma atama işleci nesne kendisine atamak çalışırsanız, hiçbir işlemi gerçekleştiren bir koşul deyimi ekleyin.  
  
    ```cpp  
    if (this != &other)  
    {  
    }  
    ```  
  
3.  Koşullu deyiminde (örneğin bellek) tüm kaynaklar için atanan bir nesneden boş.  
  
     Aşağıdaki örnek boşaltır `_data` için atanan nesnesinden üye:  
  
    ```cpp  
    // Free the existing resource.  
    delete[] _data;  
    ```  
  
     Adım 2 ve 3'te veri üyeleri kaynak nesneden oluşturulmuyor nesnesine aktarmak için ilk yordamı izleyin:  
  
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
  
4.  Aşağıdaki örnekte gösterildiği gibi geçerli bir nesneye başvuru döndürün:  
  
    ```cpp  
    return *this;  
    ```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, tam taşıma oluşturucusu ve taşıma atama işlecine gösterir `MemoryBlock` sınıfı:  
  
```cpp  
// Move constructor.  
MemoryBlock(MemoryBlock&& other)  
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
MemoryBlock& operator=(MemoryBlock&& other)  
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
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnekte nasıl taşıma semantiği uygulamalarınızın performansını gösterir. Örnek bir vektör nesnesine iki öğe ekler ve ardından iki var olan öğeler arasında yeni bir öğe ekler. `vector` Sınıfı kullanır kopyalayarak yerine vektör öğelerini taşıyarak ekleme işlemi verimli bir şekilde gerçekleştirmek için semantiği taşıyın.  
  
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
  
 Bu örnek şu çıkışı üretir:  
  
```  
In MemoryBlock(size_t). length = 25.  
In MemoryBlock(MemoryBlock&&). length = 25. Moving resource.  
In ~MemoryBlock(). length = 0.  
In MemoryBlock(size_t). length = 75.  
In MemoryBlock(MemoryBlock&&). length = 25. Moving resource.  
In ~MemoryBlock(). length = 0.  
In MemoryBlock(MemoryBlock&&). length = 75. Moving resource.  
In ~MemoryBlock(). length = 0.  
In MemoryBlock(size_t). length = 50.  
In MemoryBlock(MemoryBlock&&). length = 50. Moving resource.  
In MemoryBlock(MemoryBlock&&). length = 50. Moving resource.  
In operator=(MemoryBlock&&). length = 75.  
In operator=(MemoryBlock&&). length = 50.  
In ~MemoryBlock(). length = 0.  
In ~MemoryBlock(). length = 0.  
In ~MemoryBlock(). length = 25. Deleting resource.  
In ~MemoryBlock(). length = 50. Deleting resource.  
In ~MemoryBlock(). length = 75. Deleting resource.  
```  
  
 Visual Studio 2010'dan önce bu örnekte aşağıdaki çıkış üretilen:  
  
```  
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
  
 Sürümü kullanan semantiği taşımak bu örnek, daha az kopyalama, bellek ayırma ve bellek ayırmayı kaldırma işlemleri gerçekleştirdiğinden, taşıma semantiği kullanmayan sürümden daha verimli olur.  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Kaynak sızıntıları önlemek için her zaman içinde taşıma atama işleci (örneğin, bellek, dosya tanıtıcıları ve yuva) kaynakları serbest.  
  
 Kaynakların kurtarılamaz yok etme önlemek için düzgün şekilde taşıma atama işleci, kendi kendine atama işleyin.  
  
 Sınıfı için bir taşıma oluşturucusuna ve taşıma atama işleci sağlarsanız, taşıma atama işleci çağırmak için taşıma oluşturucusuna yazarak yedekli kod ortadan kaldırabilirsiniz. Aşağıdaki örnek taşıma atama işleci çağırır taşıma oluşturucusuna yeniden düzenlenen bir sürümünün gösterir:  
  
```  
// Move constructor.  
MemoryBlock(MemoryBlock&& other)  
   : _data(nullptr)  
   , _length(0)  
{  
   *this = std::move(other);  
}  
```  
  
 [Std::move](../standard-library/utility-functions.md#move) işlevi korur rvalue özelliği `other` parametresi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md)   
 [\<yardımcı programı > taşıma](http://msdn.microsoft.com/en-us/abef7e85-9dd6-4724-85da-d7f7fe95dca9)