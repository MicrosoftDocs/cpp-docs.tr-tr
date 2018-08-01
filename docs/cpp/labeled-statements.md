---
title: Etiketli deyimler | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- labeled statement
- statements, labeled
ms.assetid: 456a26d5-0fcc-4d1a-b71f-fa9ff3d73b91
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f5c5d626f51778782f41f4f16b7e23ad4c5acb73
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/01/2018
ms.locfileid: "39404453"
---
# <a name="labeled-statements"></a>Etiketli Deyimler
Etiketler, program denetiminin doğrudan belirtilen deyime aktarmak için kullanılır.  
  
```  
identifier :  statement  
case constant-expression :  statement  
default :  statement  
```  
  
 Etiket kapsamı içinde bildirildiği tüm işlevdir.  
  
## <a name="remarks"></a>Açıklamalar  
 Üç etiketli deyim türü vardır. Tümü, bir etiket türünü deyimden ayırmak için iki nokta üst üste kullanır. Durumu ve varsayılan etiketler, case deyimleri için özeldir.  
  
```cpp  
#include <iostream>   
using namespace std;   
  
void test_label(int x) {  
  
    if (x == 1){  
        goto label1;  
    }  
    goto label2;  
  
label1:  
    cout << "in label1" << endl;  
    return;  
  
label2:  
    cout << "in label2" << endl;  
    return;  
}  
  
int main() {  
    test_label(1);  // in label1   
    test_label(2);  // in label2  
}  
```  
  
 **Goto deyimi**  
  
 Görünümünü bir *tanımlayıcı* etiket kaynak programda bir etiket bildirir. Yalnızca bir [goto](../cpp/goto-statement-cpp.md) deyimi denetim aktarabilir bir *tanımlayıcı* etiketi. Aşağıdaki kod parçası kullanışını **goto** deyimi ve *tanımlayıcısı* etiketi:  
  
 Etiket kendi başına görünemez, her zaman bir deyime bağlı olmalıdır. Tek başına bir etiket gerekiyorsa, etiketten sonra boş bir deyim koyun.  
  
 Etiket, işlev kapsamına sahiptir ve işlev içinde tekrar bildirilemez. Ancak aynı ad, farklı işlevlerde bir etiket olarak kullanılabilir.  
  
```cpp 
// labels_with_goto.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   using namespace std;  
   goto Test2;  
  
   cout << "testing" << endl;  
  
   Test2:  
      cerr << "At Test2 label." << endl;  
}  
  
//Output: At Test2 label.  
```  
  
 **Case deyimi**  
  
 Sonra görünen etiketlerin **çalışması** anahtar sözcüğü dışında da alamaz bir **geçiş** deyimi. (Bu kısıtlama için de geçerlidir. **varsayılan** anahtar sözcüğü.) Aşağıdaki kod parçası doğru kullanımını gösterir **çalışması** etiketleri:  
  
```cpp 
// Sample Microsoft Windows message processing loop.  
switch( msg )  
{  
   case WM_TIMER:    // Process timer event.  
      SetClassWord( hWnd, GCW_HICON, ahIcon[nIcon++] );  
      ShowWindow( hWnd, SW_SHOWNA );  
      nIcon %= 14;  
      Yield();  
      break;  
  
   case WM_PAINT:  
      memset( &ps, 0x00, sizeof(PAINTSTRUCT) );  
      hDC = BeginPaint( hWnd, &ps );   
      EndPaint( hWnd, &ps );  
      break;  
  
   default:  
      // This choice is taken for all messages not specifically  
      //  covered by a case statement.  
  
      return DefWindowProc( hWnd, Message, wParam, lParam );  
      break;  
}  
```  
  
## <a name="labels-in-the-case-statement"></a>Case deyiminde etiketleri  
 Sonra görünen etiketlerin **çalışması** anahtar sözcüğü dışında da alamaz bir **geçiş** deyimi. (Bu kısıtlama için de geçerlidir. **varsayılan** anahtar sözcüğü.) Aşağıdaki kod parçası doğru kullanımını gösterir **çalışması** etiketleri:  
  
```cpp 
// Sample Microsoft Windows message processing loop.  
switch( msg )  
{  
   case WM_TIMER:    // Process timer event.  
      SetClassWord( hWnd, GCW_HICON, ahIcon[nIcon++] );  
      ShowWindow( hWnd, SW_SHOWNA );  
      nIcon %= 14;  
      Yield();  
      break;  
  
   case WM_PAINT:  
      // Obtain a handle to the device context.  
      // BeginPaint will send WM_ERASEBKGND if appropriate.  
  
      memset( &ps, 0x00, sizeof(PAINTSTRUCT) );  
      hDC = BeginPaint( hWnd, &ps );  
  
      // Inform Windows that painting is complete.  
  
      EndPaint( hWnd, &ps );  
      break;  
  
   case WM_CLOSE:  
      // Close this window and all child windows.  
  
      KillTimer( hWnd, TIMER1 );  
      DestroyWindow( hWnd );  
      if ( hWnd == hWndMain )  
         PostQuitMessage( 0 );  // Quit the application.  
      break;  
  
   default:  
      // This choice is taken for all messages not specifically  
      //  covered by a case statement.  
  
      return DefWindowProc( hWnd, Message, wParam, lParam );  
      break;  
}  
```  
  
## <a name="labels-in-the-goto-statement"></a>Goto deyimi etiketler  
 Görünümünü bir *tanımlayıcı* etiket kaynak programda bir etiket bildirir. Yalnızca bir [goto](../cpp/goto-statement-cpp.md) deyimi denetim aktarabilir bir *tanımlayıcı* etiketi. Aşağıdaki kod parçası kullanışını **goto** deyimi ve *tanımlayıcısı* etiketi:  
  
 Etiket kendi başına görünemez, her zaman bir deyime bağlı olmalıdır. Tek başına bir etiket gerekiyorsa, etiketten sonra boş bir deyim koyun.  
  
 Etiket, işlev kapsamına sahiptir ve işlev içinde tekrar bildirilemez. Ancak aynı ad, farklı işlevlerde bir etiket olarak kullanılabilir.  
  
```cpp 
// labels_with_goto.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   using namespace std;  
   goto Test2;  
  
   cout << "testing" << endl;  
  
   Test2:  
      cerr << "At Test2 label." << endl;  
// At Test2 label.  
}  
```  
  
## <a name="see-also"></a>Ayrıca bkz.  
 [C++ deyimlerine genel bakış](../cpp/overview-of-cpp-statements.md)   
 [switch Deyimi (C++)](../cpp/switch-statement-cpp.md)