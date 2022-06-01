# Doublylinked-list

// reverse the list--->

package com.company;
import java.util.Scanner;

    class DLL {
        Node head;
        Node tail;
        int size;

        public DLL() {
            int size = 0;
        }

        class Node {
            int value;
            Node next;
            Node prev;

            public Node(int value) {
                this.value = value;
            }

            public Node(int value, Node next, Node prev) {
                this.value = value;
                this.next = next;
                this.prev = prev;
            }
        }


        public void reverse() {
            if (head == null) {
                return;
            }
            Node prev = null;
            Node present = head;
            Node next = present.next;
            while (present != null) {
                present.next = prev;
                prev = present;
                present = next;

                if (next != null) {
                    next = next.next;
                }
            }
            head = prev;
        }

        public void insertLast(int value) {

            Node node = new Node(value);
            if (head == null) {
                head = node;
                return;
            }
            Node currentNode = head;
            while (currentNode.next != null) {
                currentNode = currentNode.next;
            }
            currentNode.next = node;
        }

        public void display() {
            Node temp = head;
            if (head == null) {
                System.out.println("List is null");
            }
            while (temp != null) {
                System.out.print(temp.value + " ");
                temp = temp.next;
            }
        }
    }
public class Main {
    public static void main(String[] args) {
        // write your code here
       DLL list = new DLL();
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        for (int i = 0; i < n; i++) {
            int x = sc.nextInt();
           list. insertLast(x);
        } list.reverse();
            list.display();
    }
}
