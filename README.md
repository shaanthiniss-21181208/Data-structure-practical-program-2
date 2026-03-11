# Data-struct# Node class
class Node:
    def __init__(self, song):
        self.song = song
        self.next = None


# Linked List class
class Playlist:
    def __init__(self):
        self.head = None

    # Add song to playlist
    def add_song(self, song):
        new_node = Node(song)

        if self.head is None:
            self.head = new_node
            return

        temp = self.head
        while temp.next:
            temp = temp.next

        temp.next = new_node

    # Display playlist
    def show_playlist(self):
        temp = self.head
        if temp is None:
            print("Playlist is empty")
            return

        print("Music Playlist:")
        while temp:
            print(temp.song)
            temp = temp.next

    # Delete a song
    def delete_song(self, song):
        temp = self.head

        if temp and temp.song == song:
            self.head = temp.next
            return

        prev = None
        while temp and temp.song != song:
            prev = temp
            temp = temp.next

        if temp is None:
            print("Song not found")
            return

        prev.next = temp.next


# Real-time usage
p = Playlist()

p.add_song("Song 1")
p.add_song("Song 2")
p.add_song("Song 3")

p.show_playlist()

print("\nAfter deleting Song 2:")
p.delete_song("Song 2")
p.show_playlist()ure-practical-program-2 
