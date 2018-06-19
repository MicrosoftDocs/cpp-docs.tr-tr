---
title: Özellik dizini bildirimi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- indexers
- default indexers
- defaults, indexers
- indexed properties, C++
ms.assetid: d898fdbc-2106-4b6a-8c5c-9f511d80fc2f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 76473ce04cdf5860476b7612ddcbf00b40a0fae1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33160842"
---
# <a name="property-index-declaration"></a>Özellik Dizini Bildirimi
Dizinli bir özelliği bildirme sözdizimi, Visual C++ için C++ için Yönetilen Uzantılar'dan değişmiştir.  
  
 Dizinli Özellikler Yönetilen Uzantılar dil desteğinin iki birincil eksiklikleri sınıf düzeyi alt simge oluşturma Sağlanamaması durumunda olduğundan; diğer bir deyişle, tüm Dizinli Özellikler bir ad vermeniz istenir ve bu nedenle bir yolu yoktur, örneğin, doğrudan uygulanabilir yönetilen bir alt simge işleci sağlamak için bir `Vector` veya `Matrix` sınıf nesnesi. Bir eksiklik daha az saniyedir bir özelliği bir dizinlenmiş özelliğinden ayırt etmek görsel olarak zordur - parametrelerin sayısı yalnızca göstergesidir. Son olarak, bu dizine olmayan özelliklerinin olarak aynı sorunlardaki Dizinli Özellikler yaşar - erişimciler değil atomik bir birim olarak kabul edilir, ancak ayrı ayrı yöntemlere.  Örneğin:  
  
```  
public __gc class Vector;  
public __gc class Matrix {  
   float mat[,];  
  
public:   
   __property void set_Item( int r, int c, float value);  
   __property float get_Item( int r, int c );  
  
   __property void set_Row( int r, Vector* value );  
   __property Vector* get_Row( int r );  
};  
```  
  
 Burada gördüğünüz gibi dizin oluşturucular iki belirtin veya tek ek parametreler yalnızca göre ayırt edilen boyut dizini. Yeni sözdiziminde Dizinleyicileri adından dizin oluşturucu ve sayısını ve her dizin türünü belirten bir ayraç ([,]) ayırt edilir:  
  
```  
public ref class Vector {};  
public ref class Matrix {  
private:  
   array<float, 2>^ mat;  
  
public:  
   property float Item [int,int] {  
      float get( int r, int c );  
      void set( int r, int c, float value );  
   }  
  
   property Vector^ Row [int] {  
      Vector^ get( int r );  
      void set( int r, Vector^ value );  
   }  
};  
```  
  
 Doğrudan yeni sözdiziminde sınıfın nesnelerini uygulanabilir sınıf düzeyinde dizin oluşturucu belirtmek için `default` anahtar sözcüğü yeniden için açıkça bir ad yerine. Örneğin:  
  
```  
public ref class Matrix {  
private:  
   array<float, 2>^ mat;  
  
public:  
   // ok: class level indexer now  
   //  
   //     Matrix mat;  
   //     mat[ 0, 0 ] = 1;   
   //  
   // invokes the set accessor of the default indexer  
  
   property float default [int,int] {  
      float get( int r, int c );  
      void set( int r, int c, float value );  
   }  
  
   property Vector^ Row [int] {  
      Vector^ get( int r );  
      void set( int r, Vector^ value );  
   }  
};  
```  
  
 Yeni sözdiziminde varsayılan dizin oluşturulmuş özellik belirtilmiş, aşağıdaki iki ad ayrılmış: `get_Item` ve `set_Item`. Bu varsayılan dizin oluşturulmuş özellik için oluşturulmuş temel alınan adlarıdır olmasıdır.  
  
 Hiçbir Basit Dizin sözdizimi basit özellik sözdizimine benzer olduğunu unutmayın.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfta veya Arabirimde Üye Bildirimleri (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 