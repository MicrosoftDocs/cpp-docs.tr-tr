---
title: "Derleyici Uyarısı (düzey 1) C4251 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4251
dev_langs: C++
helpviewer_keywords: C4251
ms.assetid: a9992038-f0c2-4fc4-a9be-4509442cbc1e
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 7c05983547cb6efb1d569d95c9154db67b76aba4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4251"></a>Derleyici Uyarısı (düzey 1) C4251
'tanımlayıcısı': Sınıf 'type' sınıfı 'type2' istemciler tarafından kullanılacak dll arabirimi olması gerekiyor  
  
 Bir sınıfla verilirken veri bozulması olasılığını en aza indirmek için [__declspec(dllexport)](../../cpp/dllexport-dllimport.md), emin olun:  
  
-   Tüm statik verilerinizi DLL'den dışarı aktarılan işlevler aracılığıyla erişimi var.  
  
-   Sınıfınızın içermesinden hiçbir yöntemi statik verileri değiştirebilirsiniz.  
  
-   Hiçbir satır içi yöntemi sınıfınızın CRT işlevleri veya statik verileri diğer kitaplık işlevleri kullanın (bkz [olası hataları geçirme CRT nesnelerini DLL sınırlar boyunca](../../c-runtime-library/potential-errors-passing-crt-objects-across-dll-boundaries.md) daha fazla bilgi için).  
  
-   Hiçbir yöntemi sınıfınızın (bağımsız olarak, satır içi kullanım) örnekleme EXE ve DLL içinde statik verileri farklılıkları olduğu türlerini kullanabilirsiniz.  
  
 Sanal işlevlere sahip bir sınıf tanımlar ve işlevleri DLL örneği oluşturmak için çağırabilirsiniz tanımlama ve delete Nesne türü tarafından sınıfları dışarı aktarma önleyebilirsiniz.  Ardından yalnızca sanal işlevler türüne çağırabilirsiniz.  
  
 Şablonları dışarı aktarma ile ilgili daha fazla bilgi için bkz: [http://support.microsoft.com/default.aspx?scid=kb;TR;269238 EN-US; 168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958).  
  
 C4251 dikkate bir tür kitaplığı'nda C++ standart bir hata ayıklama yayın derleme türetme varsa (**/MTd**) ve derleyici hata iletisi için _Container_base olduğu anlamına gelir.  
  
```  
// C4251.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4251  
```