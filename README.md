# hi-yoo
just my first Pro
I just want to wirte something
# -*- coding: utf-8 -*-

# Form implementation generated from reading ui file '框.ui'
#
# Created by: PyQt5 UI code generator 5.11.3
#
# WARNING! All changes made in this file will be lost!
import traceback
from PyQt5 import QtCore, QtGui, QtWidgets

class Ui_MainWindow(object):
    def setupUi(self, MainWindow):
        MainWindow.setObjectName("MainWindow")
        MainWindow.resize(505, 469)
        MainWindow.setCursor(QtGui.QCursor(QtCore.Qt.ArrowCursor))
        self.centralwidget = QtWidgets.QWidget(MainWindow)
        self.centralwidget.setObjectName("centralwidget")
        self.textBrowser = QtWidgets.QTextBrowser(self.centralwidget)
        self.textBrowser.setGeometry(QtCore.QRect(0, 10, 501, 231))
        self.textBrowser.setReadOnly(False)
        self.textBrowser.setObjectName("textBrowser")
        self.layoutWidget = QtWidgets.QWidget(self.centralwidget)
        self.layoutWidget.setGeometry(QtCore.QRect(120, 290, 216, 25))
        self.layoutWidget.setObjectName("layoutWidget")
        self.horizontalLayout = QtWidgets.QHBoxLayout(self.layoutWidget)
        self.horizontalLayout.setContentsMargins(0, 0, 0, 0)
        self.horizontalLayout.setObjectName("horizontalLayout")
        self.pushButton = QtWidgets.QPushButton(self.layoutWidget)
        self.pushButton.setObjectName("pushButton")
        self.horizontalLayout.addWidget(self.pushButton)
        self.lineEdit = QtWidgets.QLineEdit(self.layoutWidget)
        self.lineEdit.setObjectName("lineEdit")
        self.horizontalLayout.addWidget(self.lineEdit)
        MainWindow.setCentralWidget(self.centralwidget)
        self.menubar = QtWidgets.QMenuBar(MainWindow)
        self.menubar.setGeometry(QtCore.QRect(0, 0, 505, 23))
        self.menubar.setObjectName("menubar")
        self.menu_F = QtWidgets.QMenu(self.menubar)
        self.menu_F.setObjectName("menu_F")
        self.menu_E = QtWidgets.QMenu(self.menubar)
        self.menu_E.setObjectName("menu_E")
        MainWindow.setMenuBar(self.menubar)
        self.statusBar = QtWidgets.QStatusBar(MainWindow)
        self.statusBar.setObjectName("statusBar")
        MainWindow.setStatusBar(self.statusBar)
        self.toolBar = QtWidgets.QToolBar(MainWindow)
        self.toolBar.setObjectName("toolBar")
        MainWindow.addToolBar(QtCore.Qt.TopToolBarArea, self.toolBar)
        self.action_2 = QtWidgets.QAction(MainWindow)
        self.action_2.setMenuRole(QtWidgets.QAction.TextHeuristicRole)
        self.action_2.setObjectName("action_2")
        self.action_3 = QtWidgets.QAction(MainWindow)
        self.action_3.setObjectName("action_3")
        self.action_4 = QtWidgets.QAction(MainWindow)
        self.action_4.setObjectName("action_4")
        self.action_O = QtWidgets.QAction(MainWindow)
        self.action_O.setObjectName("action_O")
        self.action_N = QtWidgets.QAction(MainWindow)
        self.action_N.setObjectName("action_N")
        self.action_C = QtWidgets.QAction(MainWindow)
        self.action_C.setObjectName("action_C")
        self.actionaddWinAction = QtWidgets.QAction(MainWindow)
        self.actionaddWinAction.setObjectName("actionaddWinAction")
        self.menu_F.addSeparator()
        self.menu_F.addSeparator()
        self.menu_F.addAction(self.action_O)
        self.menu_F.addAction(self.action_N)
        self.menu_F.addAction(self.action_C)
        self.menubar.addAction(self.menu_F.menuAction())
        self.menubar.addAction(self.menu_E.menuAction())
        self.toolBar.addAction(self.actionaddWinAction)

        self.retranslateUi(MainWindow)
        self.action_C.triggered.connect(MainWindow.close)
        self.action_O.triggered.connect(self.opentext)
        self.pushButton.clicked.connect(self.text_show)
        QtCore.QMetaObject.connectSlotsByName(MainWindow)

    def retranslateUi(self, MainWindow):
        _translate = QtCore.QCoreApplication.translate
        MainWindow.setWindowTitle(_translate("MainWindow", "MainWindow"))
        MainWindow.setStatusTip(_translate("MainWindow", "这里是状态栏"))
        self.textBrowser.setHtml(_translate("MainWindow", "<!DOCTYPE HTML PUBLIC \"-//W3C//DTD HTML 4.0//EN\" \"http://www.w3.org/TR/REC-html40/strict.dtd\">\n"
"<html><head><meta name=\"qrichtext\" content=\"1\" /><style type=\"text/css\">\n"
"p, li { white-space: pre-wrap; }\n"
"</style></head><body style=\" font-family:\'SimSun\'; font-size:9pt; font-weight:400; font-style:normal;\">\n"
"<p style=\" margin-top:0px; margin-bottom:0px; margin-left:0px; margin-right:0px; -qt-block-indent:0; text-indent:0px;\"><span style=\" font-size:10pt; font-weight:600; color:#0000ff;\">内容显示在这</span></p></body></html>"))
        self.pushButton.setText(_translate("MainWindow", "发送"))
        self.menu_F.setTitle(_translate("MainWindow", "文件(&F)"))
        self.menu_E.setTitle(_translate("MainWindow", "编辑(&E)"))
        self.toolBar.setWindowTitle(_translate("MainWindow", "toolBar"))
        self.action_2.setText(_translate("MainWindow", "打开"))
        self.action_2.setShortcut(_translate("MainWindow", "Alt+O"))
        self.action_3.setText(_translate("MainWindow", "新建"))
        self.action_3.setShortcut(_translate("MainWindow", "Alt+N"))
        self.action_4.setText(_translate("MainWindow", "关闭"))
        self.action_4.setShortcut(_translate("MainWindow", "Alt+C"))
        self.action_O.setText(_translate("MainWindow", "打开(&O)"))
        self.action_O.setShortcut(_translate("MainWindow", "Alt+S"))
        self.action_N.setText(_translate("MainWindow", "新建(&N)"))
        self.action_C.setText(_translate("MainWindow", "关闭(&C)"))
        self.actionaddWinAction.setText(_translate("MainWindow", "addWinAction"))
        self.actionaddWinAction.setToolTip(_translate("MainWindow", "添加窗体"))

    def text_show(self):
        self.textBrowser.append(self.lineEdit.text())
        print(self.textBrowser.toPlainText())

    def opentext(self):
        self.statusBar.setStatusTip( "打开文件")
        mytext = QtWidgets.QFileDialog.getOpenFileName(None,"打开文件","./","*.log;;*.txt")
        print(mytext[0])
        try:
            with open(mytext[0],'r', encoding='utf-8') as f:
                for Flin in f:
                    print(Flin.split( ))
                    print('命令是：', Flin.split()[7])
                    print()
                    self.textBrowser.append(Flin.split()[1])
        except Exception as err:
            print("文件打开失败:没有这样色儿滴文件或文件夹")
            print(  err)
            pass
        else:
            print("文件打开成功！")
            #Flin.split( )[0:2]

if __name__ == "__main__":
    import sys
    app = QtWidgets.QApplication(sys.argv)
    MainWindow = QtWidgets.QMainWindow()
    ui = Ui_MainWindow()
    ui.setupUi(MainWindow)
    MainWindow.show()
    sys.exit(app.exec_())

