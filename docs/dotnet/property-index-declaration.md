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
ms.openlocfilehash: a6917742b285b3700548b54fef164d01c0594e5e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46380471"
---
# <a name="property-index-declaration"></a>Özellik Dizini Bildirimi

Dizinlenmiş bir özelliği bildirme söz dizimi, C++ için Visual C++ için Yönetilen Uzantılar'dan değişti.

Dizini oluşturulmuş özelliklerin Yönetilen Uzantılar dil desteği, iki birincil eksiklikleri sınıf düzeyi altsimge sağlamak yükleyememesine olur; diğer bir deyişle, tüm Dizinli Özellikler bir ad vermeniz istenir ve bu nedenle hiçbir yolu yoktur, örneğin, doğrudan uygulanabilir yönetilen bir alt simge işleci sağlamak için bir `Vector` veya `Matrix` sınıf nesnesi. İkinci bir eksiklik daha az olan dizinlenmiş bir özelliği bir özellik ayırmak görsel olarak zordur - parametre sayısı yalnızca bir göstergesidir. Son olarak, aynı sorunlardan dizini oluşturulmamış özellikler olarak dizini oluşturulan özellikler etkilese - erişimcileri değil bir atomik birim olarak kabul edilir, ancak her bir yöntem ayrılmış.  Örneğin:

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

Burada gördüğünüz gibi dizin oluşturuculardan iki belirtin veya tek ek parametreler yalnızca ile ayırt edilir boyut dizini. Yeni sözdiziminde, Dizinleyicileri, dizin oluşturucunun adını izleyen ve sayısı ve her dizin türünü belirten bir ayraç ([,]) ayırt edilir:

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

Yeni sözdiziminde sınıfındaki nesneler için doğrudan uygulanan bir sınıf düzeyi dizin belirtmek için `default` anahtar sözcüğü yeniden için açık bir ad yerine. Örneğin:

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

Yeni sözdiziminde, varsayılan dizini oluşturulan özellik belirtildi, aşağıdaki iki ad ayrılmış: `get_Item` ve `set_Item`. Bu varsayılan dizini oluşturulan özellik için oluşturulmuş temel alınan adlarıdır olmasıdır.

Hiçbir Basit Dizin sözdizimi basit özellik sözdizimine benzer olduğuna dikkat edin.

## <a name="see-also"></a>Ayrıca Bkz.

[Sınıfta veya Arabirimde Üye Bildirimleri (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)
