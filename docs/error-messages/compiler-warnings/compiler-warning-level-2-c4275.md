---
title: "Derleyici Uyarısı (Düzey 2) C4275 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4275
dev_langs: C++
helpviewer_keywords: C4275
ms.assetid: 18de967a-0a44-4dbc-a2e8-fc4c067ba909
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 46204fb7b87c556756db3debbe9bdc9031c9c343
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-2-c4275"></a>Derleyici Uyarısı (Düzey 2) C4275
olmayan - DLL arabirim classkey 'tanımlayıcısı' temel olarak kullanılan DLL arabirimi classkey 'tanımlayıcısı'  
  
 Dışarı aktarılan bir sınıf verilemedi sınıfından türetilmiş.  
  
 Bir sınıfla verilirken veri bozulması olasılığını en aza indirmek için [__declspec(dllexport)](../../cpp/dllexport-dllimport.md), emin olun:  
  
-   Tüm statik verilerinizi DLL'den dışarı aktarılan işlevler aracılığıyla erişilir.  
  
-   Sınıfınızın içermesinden hiçbir yöntemi statik verileri değiştirebilirsiniz.  
  
-   Hiçbir satır içi yöntemi sınıfınızın CRT işlevleri veya diğer kitaplık işlevleri statik verileri kullanın.  
  
-   Hiçbir satır içi sınıfı işlevleri, burada, örneğin, statik verilere CRT işlevleri veya diğer kitaplık işlevleri kullanın.  
  
-   Hiçbir yöntemi sınıfınızın (bağımsız olarak, satır içi kullanım) örnekleme EXE ve DLL içinde statik verileri farklılıkları olduğu türlerini kullanabilirsiniz.  
  
 Sanal işlevlere sahip bir sınıf tanımlar ve işlevleri DLL örneği oluşturmak için çağırabilirsiniz tanımlama ve delete Nesne türü tarafından sınıfları dışarı aktarma önleyebilirsiniz.  Ardından yalnızca sanal işlevler türüne çağırabilirsiniz.  
  
 Şablonları dışarı aktarma ile ilgili daha fazla bilgi için bkz: [http://support.microsoft.com/default.aspx?scid=kb;TR;269238 EN-US; 168958](http://support.microsoft.com/default.aspx?scid=KB;EN-US;168958).  
  
 C4275 dikkate Visual C++'da bir tür kitaplığı'nda C++ standart bir hata ayıklama yayın derleme türetme varsa (**/MTd**) ve derleyici hata iletisi için _Container_base olduğu anlamına gelir.  
  
```  
// C4275.cpp  
// compile with: /EHsc /MTd /W2 /c  
#include <vector>  
using namespace std;  
class Node;  
class __declspec(dllimport) VecWrapper : vector<Node *> {};   // C4275  
```