---
title: "Özellik bildirimi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- __property keyword
- declaring properties, C++
- property keyword [C++]
ms.assetid: de169378-a8b8-49f4-a586-76bffc9b5c9f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: c047e1efbe030591e26fb410c9b2df254734e08b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="property-declaration"></a>Özellik Bildirimi
Yönetilen bir sınıfta bir özelliği bildirme yolu C++ için Visual C++ için Yönetilen Uzantılar'dan değiştirdi.  
  
 Yönetilen Uzantılar tasarımında, her `set` veya `get` özelliği erişimcisi bağımsız bir yöntem olarak belirtilir. Her yöntem bildirimi önekine sahip `__property` anahtar sözcüğü. Yöntem adı ile ya da başlayan `set_` veya `get_` özelliği (olarak kullanıcıya görünen) gerçek adını ve ardından. Bu nedenle, bir `Vector` sağlayan bir `x` koordine `get` name özelliği, `get_x` ve kullanıcı olarak çağıracaktır `x`. Bu adlandırma kuralını ve yöntemleri ayrı belirtimi özelliğinin temel çalışma zamanı uygulaması gerçekte yansıtır. Örneğin, İşte bizim `Vector` koordinat özellikleri kümesi ile:  
  
```  
public __gc __sealed class Vector {  
public:  
   __property double get_x(){ return _x; }  
   __property double get_y(){ return _y; }  
   __property double get_z(){ return _z; }  
  
   __property void set_x( double newx ){ _x = newx; }  
   __property void set_y( double newy ){ _y = newy; }  
   __property void set_z( double newz ){ _z = newz; }  
};  
```  
  
 Bu özellik ile ilişkilendirilmiş işlevselliği kullanıma yayılan ve alır ve ilişkili ayarlar sözcüksel olarak bütünleştirin kullanıcıya gerektirir. Ayrıca, ayrıntılıdır. Daha çok C# gibi, yeni sözdiziminde `property` özelliği ve asıl adını türüne göre anahtar sözcüğü ve ardından. `set` Ve `get` erişim yöntemleri, özellik adı takip eden bir blok içinde yerleştirilir. C#, erişim yöntemi imzası belirtilir. Örneğin, yeni sözdizimine çevrilmiş kodu yukarıdaki örnekte aşağıdadır.  
  
```  
public ref class Vector sealed {   
public:  
   property double x {  
      double get() {  
         return _x;  
      }  
  
      void set( double newx ) {  
         _x = newx;  
      }  
   } // Note: no semi-colon  
};  
```  
  
 Özellik erişim yöntemleri farklı erişim düzeyleri - gibi yansıtmak durumunda bir `public get` ve `private` veya `protected set`, bir açık erişim etiketinde belirtilebilir. Varsayılan olarak, özelliğin erişim düzeyi, kapsayan erişim düzeyi yansıtır. Örneğin, yukarıdaki tanımı içinde `Vector`, her iki `get` ve `set` yöntemleri `public`. Yapmak için `set` yöntemi `protected` veya `private`, tanımı şu şekilde düzeltilmesi:  
  
```  
public ref class Vector sealed {   
public:  
   property double x {  
      double get() {  
         return _x;  
      }  
  
   private:  
      void set( double newx ) {  
         _x = newx;  
      }  
  
   } // note: extent of private culminates here  
  
// note: dot is a public method of Vector  
double dot( const Vector^ wv );  
  
// etc.  
};  
```  
  
 Özellik kapanış ayracı veya ek erişim anahtar sözcüğü belirtimi kadar bir özellik içindeki bir erişim anahtar kapsamını genişletir. Özellik tanımlandığı kapsayan erişim düzeyi için özellik tanımını ötesinde kapsamaz. Yukarıdaki bildirimde için `Vector::dot()` ortak bir yöntemdir.  
  
 Üç ayarla/al özelliklerini yazma `Vector` koordinatları üç adımdan oluşur:  
  
1.  uygun türde bir özel durum üyesi bildirin.  
  
2.  kullanıcının değeri almak istediği zaman döndürün.  
  
3.  Yeni değer atayın.  
  
 Yeni sözdiziminde bir toplu özellik, bu kullanım şekillerini otomatikleştiren kullanılabilir söz dizimi:  
  
```  
public ref class Vector sealed {   
public:  
   // equivalent shorthand property syntax  
   property double x;   
   property double y;  
   property double z;  
};  
```  
  
 Toplu özellik sözdizimi ilginç yan etkisi backstage durum üyesi derleyici tarafından üretilen karşın, bu ayarla/al erişimciler aracılığı dışında sınıf içinde erişilebilir olmamasıdır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfta veya arabirimde üye bildirimleri (C + +/ CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [property](../windows/property-cpp-component-extensions.md)