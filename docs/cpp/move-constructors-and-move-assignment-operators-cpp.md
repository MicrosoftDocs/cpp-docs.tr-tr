---
title: 'Nasıl yapılır: taşıma oluşturucuları ve taşıma atama işleçleri (C++) tanımlama | Microsoft Docs'
ms.custom: ''
ms.date: 03/05/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- move constructor [C++]
ms.assetid: e75efe0e-4b74-47a9-96ed-4e83cfc4378d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f414871477e8d263546833cb71496f5795dd4671
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43204993"
---
# <a name="move-constructors-and-move-assignment-operators-c"></a>Taşıma Oluşturucuları ve Taşıma Atama İşleçleri (C++)
Bu konu nasıl yazılacağını açıklar bir *taşıma Oluşturucu* ve bir C++ sınıfına ilişkin taşıma ataması işleci. Taşıma Oluşturucusu kopyalamadan bir lvalue taşınacak rvalue nesnesi tarafından sahip olunan kaynakları sağlar. Semantik taşıma hakkında daha fazla bilgi için bkz. [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
 Bu konuda aşağıdaki C++ sınıfını derlemeler `MemoryBlock`, bir bellek arabelleğini yöneten.  
  
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
  
 Aşağıdaki yordamlarda, bir taşıma oluşturucusuna ve taşıma atama işleci örnek C++ sınıfı için yazılacak açıklanır.  
  
### <a name="to-create-a-move-constructor-for-a-c-class"></a>Bir C++ sınıfına ilişkin taşıma Oluşturucusu oluşturmak için  
  
1.  Sınıf türü bir rvalue başvurusunu parametre olarak alan bir boş Oluşturucu yöntemi, aşağıdaki örnekte gösterildiği gibi tanımlayın:  
  
    ```cpp  
    MemoryBlock(MemoryBlock&& other)  
       : _data(nullptr)  
       , _length(0)  
    {  
    }  
    ```  
  
2.  Taşıma Kurucuda sınıfı veri üyelerini kaynak nesneden yapılandırılmakta olan nesneye atayın:  
  
    ```cpp  
    _data = other._data;  
    _length = other._length;  
    ```  
  
3.  Kaynak nesnesi veri üyeleri için varsayılan değerler atayın. Bu, yok edici kaynakları (bellek gibi) birden çok kez boşaltmasını engeller:  
  
    ```cpp  
    other._data = nullptr;  
    other._length = 0;  
    ```  
  
### <a name="to-create-a-move-assignment-operator-for-a-c-class"></a>Bir C++ sınıfına ilişkin taşıma ataması işleci oluşturmak için  

1.  Aşağıdaki örnekte gösterildiği gibi rvalue başvurusunu parametre olarak sınıf türüne alan ve sınıf türüne bir referans döndüren boş atama işleci tanımlayın:  
  
    ```cpp  
    MemoryBlock& operator=(MemoryBlock&& other)  
    {  
    }  
    ```  
  
2.  Taşıma atama operatöründe, nesneyi kendisine atamaya çalıştığınızda işlem gerçekleştirmeyecek bir koşullu ifade ekleyin.  
  
    ```cpp  
    if (this != &other)  
    {  
    }  
    ```  
  
3.  Koşullu deyimde, atanan nesneden tüm kaynakları (bellek gibi) boş.  
  
     Aşağıdaki örnek boşaltır `_data` üyesini şuna atanan nesneden:  
  
    ```cpp  
    // Free the existing resource.  
    delete[] _data;  
    ```  
  
     2. ve 3 veri üyelerini kaynak nesneden yapılandırılmakta olan nesneye aktarmak için ilk yordamdaki adımları izleyin:  
  
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
  
4.  Aşağıdaki örnekte gösterildiği gibi geçerli nesneye bir başvuru döndürür:  
  
    ```cpp  
    return *this;  
    ```  
  
## <a name="example"></a>Örnek  
 Aşağıdaki örnek, tam taşıma oluşturucu ve taşıma atama işlecine için gösterir `MemoryBlock` sınıfı:  
  
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
 Aşağıdaki örnek, taşıma semantiği, uygulamalarınızın performansını nasıl geliştireceğiniz gösterir. Bu örnek, bir vektör nesnesine iki öğe ekler ve ardından varolan iki öğe arasındaki yeni bir öğe ekler. `vector` Taşıma semantiği öğeleri vektör elementini kopyalamak yerine taşıyarak ekleme işlemini verimli bir şekilde gerçekleştirmek için sınıfı kullanır.  
  
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
  
 Visual Studio 2010'dan önce bu örnek aşağıdaki çıktıyı üretilen:  
  
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
  
 Taşıma semantiği kullanan bu örneğinin sürümü, daha az kopyalama, bellek ayırma ve bellek birleştirme işlemi gerçekleştirdiğinden, taşıma semantiği kullanmayan sürümünden daha etkilidir.  
  
## <a name="robust-programming"></a>Güçlü Programlama  
 Kaynak sızıntılarını önlemek için her zaman kaynakları (örneğin, bellek, dosya tanıtıcıları ve yuvaları) taşıma ataması işlecinde serbest bırakın.  
  
 Kaynakların kurtarılamayacak şekilde yok edilmesini önlemek için taşıma ataması işlecinde kendi kendine atamayı düzgün bir şekilde işleyin.  
  
 Sınıfınız için hem bir taşıma oluşturucusuna ve taşıma atama işleci sağlarsanız, taşıma atama işlecini çağırmak için taşıma kurucunuzu yazarak artıklı kodu çıkarabilirsiniz. Aşağıdaki örnek, taşıma atama işlecini çağıran bir taşıma Oluşturucusu düzeltilmiş bir hali gösterilmektedir:  
  
```cpp
// Move constructor.  
MemoryBlock(MemoryBlock&& other)  
   : _data(nullptr)  
   , _length(0)  
{  
   *this = std::move(other);  
}  
```  
  
 [Std::move](../standard-library/utility-functions.md#move) işlevi rvalue özelliğini korur *diğer* parametresi.  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [Rvalue başvuru Bildirimcisi: & &](../cpp/rvalue-reference-declarator-amp-amp.md)   
 [\<yardımcı programı > Taşı](https://msdn.microsoft.com/abef7e85-9dd6-4724-85da-d7f7fe95dca9)